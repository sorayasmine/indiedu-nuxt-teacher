<template>
  <footer class="w-full">
    <div
      class="w-full grid grid-cols-4 lg:grid-cols-10 gap-12 px-4 sm:px-10 md:px-4 lg:px-20 py-20"
    >
      <div class="col-span-4 space-y-4">
        <nuxt-link to="/" class="flex items-center">
          <img :src="require('@/assets/img/illust/logo.svg')" class="" alt="" />
          <span
            class="font-bold text-lg tracking-wide ml-2 font-rubik text-gray-900"
          >
            Indiedu
          </span>
        </nuxt-link>
        <p class="text-secondaryText leading-7 tracking-wide">
          Konsep belajar alternatif yang dikembangkan oleh Indiedu dengan tujuan
          memelihara dan memperkuat kemampuan belajar siswa
        </p>
      </div>
      <div class="col-span-2 space-y-4">
        <h5 class="text-lg font-bold text-primaryText">Bantuan</h5>
        <div class="flex flex-col space-y-2">
          <nuxt-link to="/signup" class="text-secondaryText"
            >Daftar Kelas</nuxt-link
          >
          <nuxt-link to="/signup" class="text-secondaryText"
            >Jadi Pengajar</nuxt-link
          >
          <nuxt-link to="/privacy-policy" class="text-secondaryText"
            >Kebijakan Privasi</nuxt-link
          >
        </div>
      </div>
      <div class="col-span-2 space-y-4">
        <h5 class="text-lg font-bold text-primaryText">Social media</h5>
        <div class="flex flex-col space-y-2">
          <a
            href="https://www.instagram.com/"
            class="text-secondaryText"
            target="_blank"
            >Instagram</a
          >
          <a
            href="https://facebook.com/"
            class="text-secondaryText"
            target="_blank"
            >Facebook</a
          >
        </div>
      </div>
      <div class="col-span-2 space-y-4">
        <h5 class="text-lg font-bold text-primaryText">Bantuan</h5>
        <div class="flex flex-col space-y-2">
          <a
            href="https://goo.gl/maps/FpC9YpNe8cw9a4Fk7"
            class="text-secondaryText"
            target="_blank"
          >
            Jalan Suka Sari Bandung, Jawa Barat
          </a>
        </div>
      </div>
    </div>
    <div class="w-full text-center py-6">
      <h5 class="text-lg font-bold text-primaryText">
        © 2021. Indiedu. Powered by PT. Ihsan
      </h5>
    </div>
  </footer>
</template>
