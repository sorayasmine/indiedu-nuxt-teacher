<template>
  <section>
    <div>
      <div class="flex items-center justify-center">
        <h1 class="text-primaryText text-3xl font-bold pb-8">
          Daftar dan Dapatkan Akses Kelas Gratis
        </h1>
      </div>
      <ValidationObserver ref="signupForm" v-slot="{ handleSubmit }">
        <form class="" novalidate @submit.prevent="handleSubmit(register)">
          <div class="grid place-items-center justify-items-center space-y-4">
            <div class="grid gap-4 rounded-md w-3/12">
              <ValidationProvider
                v-slot="{ errors }"
                name="name"
                rules="required|min:5"
              >
                <input
                  v-model="name"
                  class="w-full bg-secondaryGrey-6 placeholder-secondaryGrey-4 text-primary font-medium border-0 rounded-sm focus:text-primary"
                  rules="required"
                  type="text"
                  placeholder="Nama Lengkap"
                />
                <br />
                <span id="nameHelp" class="text-sm text-red-700">{{
                  errors[0]
                }}</span>
              </ValidationProvider>
              <ValidationProvider
                v-slot="{ errors }"
                name="email"
                rules="required|email"
              >
                <input
                  id="email"
                  v-model="email"
                  class="w-full bg-secondaryGrey-6 placeholder-secondaryGrey-4 text-primary font-medium border-0 rounded-sm focus:text-primary"
                  type="email"
                  placeholder="Alamat Email"
                />
                <br />
                <span id="emailHelp" class="text-sm text-red-700">{{
                  errors[0]
                }}</span>
              </ValidationProvider>
              <ValidationProvider
                v-slot="{ errors }"
                name="password"
                rules="required|min:6"
                class="relative"
              >
                <input
                  v-model="password"
                  class="w-full bg-secondaryGrey-6 placeholder-secondaryGrey-4 text-primary font-medium border-0 rounded-sm focus:text-primary"
                  rules="required|min:6"
                  :type="[showPassword ? 'text' : 'password']"
                  placeholder="Password"
                />
                <div
                  class="inline absolute right-0 p-2 text-secondaryGrey-5 hover:text-secodaryGrey-6"
                  @click="showPassword = !showPassword"
                >
                  <svg
                    xmlns="http://www.w3.org/2000/svg"
                    class="h-5 w-5"
                    viewBox="0 0 20 20"
                    fill="currentColor"
                  >
                    <path
                      v-if="showPassword"
                      d="M10 12a2 2 0 100-4 2 2 0 000 4z"
                    />
                    <path
                      v-if="showPassword"
                      fill-rule="evenodd"
                      d="M.458 10C1.732 5.943 5.522 3 10 3s8.268 2.943 9.542 7c-1.274 4.057-5.064 7-9.542 7S1.732 14.057.458 10zM14 10a4 4 0 11-8 0 4 4 0 018 0z"
                      clip-rule="evenodd"
                    />
                    <path
                      v-if="!showPassword"
                      fill-rule="evenodd"
                      d="M3.707 2.293a1 1 0 00-1.414 1.414l14 14a1 1 0 001.414-1.414l-1.473-1.473A10.014 10.014 0 0019.542 10C18.268 5.943 14.478 3 10 3a9.958 9.958 0 00-4.512 1.074l-1.78-1.781zm4.261 4.26l1.514 1.515a2.003 2.003 0 012.45 2.45l1.514 1.514a4 4 0 00-5.478-5.478z"
                      clip-rule="evenodd"
                    />
                    <path
                      v-if="!showPassword"
                      d="M12.454 16.697L9.75 13.992a4 4 0 01-3.742-3.741L2.335 6.578A9.98 9.98 0 00.458 10c1.274 4.057 5.065 7 9.542 7 .847 0 1.669-.105 2.454-.303z"
                    />
                  </svg>
                </div>
                <br />
                <span id="passwordHelp" class="text-sm text-red-700">{{
                  errors[0]
                }}</span>
              </ValidationProvider>
            </div>
            <button
              class="block w-3/12 px-4 py-3 font-semibold text-white transition duration-500 ease-in-out transform bg-primary rounded-md hover:bg-primary-400 focus:shadow-outline focus:outline-none focus:ring-2 focus:ring-bg-primary-400 ring-offset-current ring-offset-2"
            >
              Daftar
            </button>
            <div class="flex items-center justify-between">
              <span class="border-b border-black w-1/5 md:w-1/4"></span>
              <p class="text-sm text-primary">atau</p>
              <span class="border-b border-black w-1/5 md:w-1/4"></span>
            </div>
            <div class="w-3/12">
              <a
                href="#"
                class="flex items-center justify-center bg-secondaryGrey-6 rounded-lg shadow-md hover:bg-secondaryGrey"
              >
                <div>
                  <svg class="h-6 w-6" viewBox="0 0 40 40">
                    <path
                      d="M36.3425 16.7358H35V16.6667H20V23.3333H29.4192C28.045 27.2142 24.3525 30 20 30C14.4775 30 10 25.5225 10 20C10 14.4775 14.4775 9.99999 20 9.99999C22.5492 9.99999 24.8683 10.9617 26.6342 12.5325L31.3483 7.81833C28.3717 5.04416 24.39 3.33333 20 3.33333C10.7958 3.33333 3.33335 10.7958 3.33335 20C3.33335 29.2042 10.7958 36.6667 20 36.6667C29.2042 36.6667 36.6667 29.2042 36.6667 20C36.6667 18.8825 36.5517 17.7917 36.3425 16.7358Z"
                      fill="#FFC107"
                    />
                    <path
                      d="M5.25497 12.2425L10.7308 16.2583C12.2125 12.59 15.8008 9.99999 20 9.99999C22.5491 9.99999 24.8683 10.9617 26.6341 12.5325L31.3483 7.81833C28.3716 5.04416 24.39 3.33333 20 3.33333C13.5983 3.33333 8.04663 6.94749 5.25497 12.2425Z"
                      fill="#FF3D00"
                    />
                    <path
                      d="M20 36.6667C24.305 36.6667 28.2167 35.0192 31.1742 32.34L26.0159 27.975C24.3425 29.2425 22.2625 30 20 30C15.665 30 11.9842 27.2359 10.5975 23.3784L5.16254 27.5659C7.92087 32.9634 13.5225 36.6667 20 36.6667Z"
                      fill="#4CAF50"
                    />
                    <path
                      d="M36.3425 16.7358H35V16.6667H20V23.3333H29.4192C28.7592 25.1975 27.56 26.805 26.0133 27.9758C26.0142 27.975 26.015 27.975 26.0158 27.9742L31.1742 32.3392C30.8092 32.6708 36.6667 28.3333 36.6667 20C36.6667 18.8825 36.5517 17.7917 36.3425 16.7358Z"
                      fill="#1976D2"
                    />
                  </svg>
                </div>
                <h1
                  class="text-base font-medium px-4 py-3 text-center text-secondaryGrey-7"
                >
                  Daftar dengan Google
                </h1>
              </a>
            </div>
            <p class="font-medium text-base text-secondaryGrey-7">
              Sudah punya akun?
              <nuxt-link
                to="/auth/login"
                class="font-semibold text-primary hover:text-primary-400"
                >Masuk
              </nuxt-link>
            </p>
            <div class="w-3/12">
              <p class="text-primary text-xs">
                "By signing up you agree to
                <strong> Indiedu Terms of Service </strong> and
                <strong>Privacy Policy</strong>. This page is protected by
                reCAPTCHA and is subject to Google's terms of
                <strong>Service </strong>and <strong>Privacy Policy</strong>"
              </p>
            </div>
          </div>
        </form>
      </ValidationObserver>
    </div>
  </section>
</template>

<script>
import { ValidationObserver, ValidationProvider } from 'vee-validate'

export default {
  name: 'AuthRegister',
  components: {
    ValidationObserver,
    ValidationProvider,
  },
  layout: 'guest',
  data() {
    return {
      name: '',
      email: '',
      password: '',
      showPassword: false,
    }
  },
  methods: {
    async register() {
      try {
        const result = await this.$axios.$post('/register', {
          email: this.email,
          password: this.password,
          name: this.email,
        })
        console.log(result)
      } catch (err) {
        console.log('error', err.response.data)
      }
    },
  },
}
</script>
