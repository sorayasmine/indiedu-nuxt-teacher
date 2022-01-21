<template>
  <nuxt-link to="/" class="flex md:items-center">
    <img
      :src="require('@/assets/img/illust/logo.svg')"
      class="w-6 xl:w-8"
      alt=""
    />
    <span
      class="font-bold text-base xl:text-lg tracking-wide ml-2 font-rubik text-gray-900"
    >
      Indiedu
    </span>
  </nuxt-link>
</template>

<script>
export default {
  name: 'AppLogo',
}
</script>
