<template>
  <div class="w-full px-20 py-10">
    <div class="mx-auto">
      <form action="#" method="POST">
        <div class="shadow sm:rounded-md sm:overflow-hidden">
          <div class="px-4 py-5 bg-white space-y-6 sm:p-6">
            <h2 class="text-2xl font-bold leading-tight text-primaryText">
              Pengaturan Profil
            </h2>

            <div>
              <label class="block text-sm font-medium text-gray-700">
                Foto
              </label>
              <div class="mt-1 flex items-center">
                <span
                  class="inline-block h-12 w-12 rounded-full overflow-hidden bg-gray-100"
                >
                  <img
                    :src="profilePreview"
                    class="h-full w-full object-cover object-center"
                    alt=""
                  />
                </span>
                <input
                  type="file"
                  class="ml-5 bg-white py-2 px-3 border border-gray-300 rounded-md shadow-sm text-sm leading-4 font-medium text-gray-700 hover:bg-gray-50 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-primary"
                  @change="profileImagePreview"
                />
              </div>
            </div>

            <div>
              <label
                for="about"
                class="block text-sm font-medium text-gray-700"
              >
                Tentang Saya
              </label>
              <div class="mt-1">
                <textarea
                  id="about"
                  name="about"
                  rows="3"
                  class="shadow-sm focus:ring-primary focus:border-primary mt-1 block w-full sm:text-sm border border-gray-300 rounded-md"
                  placeholder="Saya seorang anak sma kelas 3..."
                ></textarea>
              </div>
              <p class="mt-2 text-sm text-gray-500">
                Deskripsi singkat untuk profil Anda.
              </p>
            </div>

            <div>
              <label class="block text-sm font-medium text-gray-700">
                Foto Sampul
              </label>
              <div
                class="mt-1 flex justify-center px-6 pt-5 pb-6 border-2 border-gray-300 border-dashed rounded-md"
              >
                <div v-if="!coverImageUrl" class="space-y-1 text-center">
                  <svg
                    class="mx-auto h-12 w-12 text-gray-400"
                    stroke="currentColor"
                    fill="none"
                    viewBox="0 0 48 48"
                    aria-hidden="true"
                  >
                    <path
                      d="M28 8H12a4 4 0 00-4 4v20m32-12v8m0 0v8a4 4 0 01-4 4H12a4 4 0 01-4-4v-4m32-4l-3.172-3.172a4 4 0 00-5.656 0L28 28M8 32l9.172-9.172a4 4 0 015.656 0L28 28m0 0l4 4m4-24h8m-4-4v8m-12 4h.02"
                      stroke-width="2"
                      stroke-linecap="round"
                      stroke-linejoin="round"
                    />
                  </svg>
                  <div class="flex text-sm text-gray-600">
                    <label
                      for="file-upload"
                      class="relative cursor-pointer bg-white rounded-md font-medium text-primaryText hover:text-primary focus-within:outline-none focus-within:ring-2 focus-within:ring-offset-2 focus-within:ring-primary"
                    >
                      <span>Upload file</span>
                      <input
                        id="file-upload"
                        name="file-upload"
                        type="file"
                        class="sr-only"
                        @change="coverImagePreview"
                      />
                    </label>
                    <p class="pl-1">atau drag file kesini</p>
                  </div>
                  <p class="text-xs text-gray-500">PNG, JPG up to 5MB</p>
                </div>
                <div v-show="coverPreview" class="w-full relative">
                  <div
                    class="inline-block cursor-pointer absolute top-0 right-0 text-primary z-50 m-4 p-2 shadow bg-white rounded-full"
                    @click="closeCoverPreview"
                  >
                    <svg
                      xmlns="http://www.w3.org/2000/svg"
                      class="h-6 w-6"
                      fill="none"
                      viewBox="0 0 24 24"
                      stroke="currentColor"
                    >
                      <path
                        stroke-linecap="round"
                        stroke-linejoin="round"
                        stroke-width="2"
                        d="M6 18L18 6M6 6l12 12"
                      />
                    </svg>
                  </div>
                  <div
                    v-if="coverImageUrl"
                    class="w-full aspect-w-16 aspect-h-9"
                  >
                    <img
                      :src="coverImageUrl"
                      class="w-full object-cover object-center filter opacity-90"
                      alt=""
                    />
                  </div>
                </div>
              </div>
            </div>
          </div>
          <div class="px-4 py-3 bg-gray-50 text-right sm:px-6">
            <button
              type="submit"
              class="inline-flex justify-center py-2 px-4 border border-transparent shadow-sm text-sm font-medium rounded-md text-white bg-primary hover:bg-primary-400 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-primary-400 transition duration-200"
            >
              Simpan
            </button>
          </div>
        </div>
      </form>
    </div>

    <div class="hidden sm:block" aria-hidden="true">
      <div class="py-5">
        <div class="border-t border-gray-200"></div>
      </div>
    </div>

    <div class="mt-10 sm:mt-0">
      <div class="mt-5 md:mt-0 mx-auto">
        <form action="#" method="POST">
          <div class="shadow overflow-hidden sm:rounded-md">
            <div class="px-4 py-5 bg-white sm:p-6">
              <h2
                class="text-2xl font-bold leading-tight text-primaryText mb-6"
              >
                Informasi User
              </h2>
              <div class="grid grid-cols-6 gap-6">
                <div class="col-span-6 sm:col-span-3">
                  <label
                    for="name"
                    class="block text-sm font-medium text-gray-700"
                    >Nama Lengkap</label
                  >
                  <input
                    id="name"
                    type="text"
                    name="name"
                    autocomplete="given-name"
                    class="mt-1 focus:ring-primary focus:border-primary block w-full shadow-sm sm:text-sm border-gray-300 rounded-md"
                  />
                </div>

                <div class="col-span-6 sm:col-span-3">
                  <label
                    for="email"
                    class="block text-sm font-medium text-gray-700"
                    >Alamat Email</label
                  >
                  <input
                    id="email"
                    type="text"
                    name="email"
                    autocomplete="family-name"
                    class="mt-1 focus:ring-primary focus:border-primary block w-full shadow-sm sm:text-sm border-gray-300 rounded-md"
                  />
                </div>

                <div class="col-span-6 sm:col-span-3">
                  <label
                    for="no_telp"
                    class="block text-sm font-medium text-gray-700"
                    >No Telepon</label
                  >
                  <input
                    id="no_telp"
                    type="text"
                    name="no_telp"
                    autocomplete="given-no_telp"
                    class="mt-1 focus:ring-primary focus:border-primary block w-full shadow-sm sm:text-sm border-gray-300 rounded-md"
                  />
                </div>

                <div class="col-span-6 sm:col-span-3">
                  <label
                    for="nik"
                    class="block text-sm font-medium text-gray-700"
                    >NIK</label
                  >
                  <input
                    id="nik"
                    type="text"
                    name="nik"
                    autocomplete="given-nik"
                    class="mt-1 focus:ring-primary focus:border-primary block w-full shadow-sm sm:text-sm border-gray-300 rounded-md"
                  />
                </div>

                <div class="col-span-6 sm:col-span-3">
                  <label
                    for="tempat_lahir"
                    class="block text-sm font-medium text-gray-700"
                    >Tempat Lahir</label
                  >
                  <input
                    id="tempat_lahir"
                    type="text"
                    name="tempat_lahir"
                    autocomplete="given-tempat_lahir"
                    class="mt-1 focus:ring-primary focus:border-primary block w-full shadow-sm sm:text-sm border-gray-300 rounded-md"
                  />
                </div>
                <div class="col-span-6 sm:col-span-3">
                  <label
                    for="tanggal_lahir"
                    class="block text-sm font-medium text-gray-700"
                    >Tanggal Lahir</label
                  >
                  <datepicker
                    id="tanggal_lahir"
                    v-model="time"
                    name="tanggal_lahir"
                    input-class="w-full border focus:ring-primary focus:border-primary border-gray-300 rounded-md sm:text-sm"
                    wrapper-class="w-full-imp mt-1 p-0 block w-full shadow-sm border-none"
                    type="date"
                  ></datepicker>
                </div>

                <div class="col-span-6 sm:col-span-3">
                  <label
                    for="country"
                    class="block text-sm font-medium text-gray-700"
                    >Negara</label
                  >
                  <select
                    id="country"
                    name="country"
                    autocomplete="country-name"
                    class="mt-1 block w-full py-2 px-3 border border-gray-300 bg-white rounded-md shadow-sm focus:outline-none focus:ring-primary focus:border-primary sm:text-sm"
                  >
                    <option>Indonesia</option>
                    <option>Canada</option>
                    <option>Mexico</option>
                  </select>
                </div>

                <div class="col-span-6">
                  <label
                    for="street-address"
                    class="block text-sm font-medium text-gray-700"
                    >Alamat</label
                  >
                  <input
                    id="street-address"
                    type="text"
                    name="street-address"
                    autocomplete="street-address"
                    class="mt-1 focus:ring-primary focus:border-primary block w-full shadow-sm sm:text-sm border-gray-300 rounded-md"
                  />
                </div>

                <div class="col-span-6 sm:col-span-6 lg:col-span-2">
                  <label
                    for="city"
                    class="block text-sm font-medium text-gray-700"
                    >Kota</label
                  >
                  <input
                    id="city"
                    type="text"
                    name="city"
                    autocomplete="address-level2"
                    class="mt-1 focus:ring-primary focus:border-primary block w-full shadow-sm sm:text-sm border-gray-300 rounded-md"
                  />
                </div>

                <div class="col-span-6 sm:col-span-3 lg:col-span-2">
                  <label
                    for="region"
                    class="block text-sm font-medium text-gray-700"
                    >Daerah / Provinsi</label
                  >
                  <input
                    id="region"
                    type="text"
                    name="region"
                    autocomplete="address-level1"
                    class="mt-1 focus:ring-primary focus:border-primary block w-full shadow-sm sm:text-sm border-gray-300 rounded-md"
                  />
                </div>

                <div class="col-span-6 sm:col-span-3 lg:col-span-2">
                  <label
                    for="postal-code"
                    class="block text-sm font-medium text-gray-700"
                    >Kode Pos</label
                  >
                  <input
                    id="postal-code"
                    type="text"
                    name="postal-code"
                    autocomplete="postal-code"
                    class="mt-1 focus:ring-primary focus:border-primary block w-full shadow-sm sm:text-sm border-gray-300 rounded-md"
                  />
                </div>
              </div>
            </div>
            <div class="px-4 py-3 bg-gray-50 text-right sm:px-6">
              <button
                type="submit"
                class="inline-flex justify-center py-2 px-4 border border-transparent shadow-sm text-sm font-medium rounded-md text-white bg-primary hover:bg-primary-400 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-primary-400 transition duration-200"
              >
                Simpan
              </button>
            </div>
          </div>
        </form>
      </div>
    </div>
  </div>
</template>

<script>
import { mapGetters } from 'vuex'
import Datepicker from 'vuejs-datepicker'

export default {
  name: 'DashboardSiswaProfile',
  components: {
    Datepicker,
  },
  layout: 'dashboard-siswa',
  middleware: 'auth',
  data() {
    return {
      time: null,
      coverImageUrl: null,
      coverPreview: false,
      profilePreview:
        'https://t4.ftcdn.net/jpg/00/64/67/63/360_F_64676383_LdbmhiNM6Ypzb3FM4PPuFP9rHe7ri8Ju.jpg',
    }
  },
  head() {
    return {
      title: 'Dashboard Siswa | Indiedu',
    }
  },
  computed: {
    ...mapGetters({
      user: 'user',
    }),
  },
  methods: {
    coverImagePreview(e) {
      const file = e.target.files[0]
      this.coverImageUrl = URL.createObjectURL(file)
      this.coverPreview = true
    },
    profileImagePreview(e) {
      const file = e.target.files[0]
      this.profilePreview = URL.createObjectURL(file)
    },
    closeCoverPreview() {
      this.coverPreview = false
      this.coverImageUrl = null
    },
  },
}
</script>

<style scoped>
.w-full-imp {
  width: 100% !important;
}
</style>
