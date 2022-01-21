<template>
  <div class="w-full px-20 py-10">
    <div class="mx-auto">
      <form action="#" method="POST">
        <div class="shadow overflow-hidden sm:rounded-md">
          <div class="px-4 py-5 bg-white space-y-6 sm:p-6">
            <h2 class="text-2xl font-bold leading-tight text-primaryText">
              Pengaturan Notifikasi
            </h2>
            <fieldset>
              <legend class="text-base font-medium text-gray-900">
                Email Notification
              </legend>
              <div class="mt-4 space-y-4">
                <div class="flex items-start">
                  <div class="flex items-center h-5">
                    <input
                      id="comments"
                      name="comments"
                      type="checkbox"
                      class="focus:ring-primary-500 h-4 w-4 text-primary-500 border-gray-300 rounded"
                    />
                  </div>
                  <div class="ml-3 text-sm">
                    <label for="comments" class="font-medium text-gray-700"
                      >Update Materi</label
                    >
                    <p class="text-gray-500">
                      Dapatkan notifikasi ketika materi yang kamu beli telah
                      diupdate oleh pengajar.
                    </p>
                  </div>
                </div>
                <div class="flex items-start">
                  <div class="flex items-center h-5">
                    <input
                      id="candidates"
                      name="candidates"
                      type="checkbox"
                      class="focus:ring-primary-500 h-4 w-4 text-primary-500 border-gray-300 rounded"
                    />
                  </div>
                  <div class="ml-3 text-sm">
                    <label for="candidates" class="font-medium text-gray-700"
                      >Materi Terkait</label
                    >
                    <p class="text-gray-500">
                      Dapatkan notifikasi ketika muncul materi yang terkait
                      dengan yang sedang kamu pelajari.
                    </p>
                  </div>
                </div>
                <div class="flex items-start">
                  <div class="flex items-center h-5">
                    <input
                      id="offers"
                      name="offers"
                      type="checkbox"
                      class="focus:ring-primary-500 h-4 w-4 text-primary-500 border-gray-300 rounded"
                    />
                  </div>
                  <div class="ml-3 text-sm">
                    <label for="offers" class="font-medium text-gray-700"
                      >Penawaran</label
                    >
                    <p class="text-gray-500">
                      Dapatkan notifikasi ketika terdapat penawaran diskon/bonus
                      terbaru di Indiedu.
                    </p>
                  </div>
                </div>
              </div>
            </fieldset>
            <fieldset>
              <div>
                <legend class="text-base font-medium text-gray-900">
                  In App Notification
                </legend>
                <p class="text-sm text-gray-500">
                  Notifikasi yang akan muncul pada aplikasi web atau mobile
                  Indiedu
                </p>
              </div>
              <div class="mt-4 space-y-4">
                <div class="flex items-center">
                  <input
                    id="push-everything"
                    name="push-notifications"
                    type="radio"
                    class="focus:ring-primary-500 h-4 w-4 text-primary-500 border-gray-300"
                  />
                  <label
                    for="push-everything"
                    class="ml-3 block text-sm font-medium text-gray-700"
                  >
                    Semuanya
                  </label>
                </div>
                <div class="flex items-center">
                  <input
                    id="push-email"
                    name="push-notifications"
                    type="radio"
                    class="focus:ring-primary-500 h-4 w-4 text-primary-500 border-gray-300"
                  />
                  <label
                    for="push-email"
                    class="ml-3 block text-sm font-medium text-gray-700"
                  >
                    Sama dengan email
                  </label>
                </div>
                <div class="flex items-center">
                  <input
                    id="push-nothing"
                    name="push-notifications"
                    type="radio"
                    class="focus:ring-primary-500 h-4 w-4 text-primary-500 border-gray-300"
                  />
                  <label
                    for="push-nothing"
                    class="ml-3 block text-sm font-medium text-gray-700"
                  >
                    Jangan aktifkan notifikasi
                  </label>
                </div>
              </div>
            </fieldset>
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
</template>

<script>
export default {
  name: 'DashboardSiswaNotification',
  middleware: 'auth',
  head() {
    return {
      title: 'Dashboard Siswa | Indiedu',
    }
  },
}
</script>
