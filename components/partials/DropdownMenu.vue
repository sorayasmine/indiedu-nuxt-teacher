<template>
  <transition name="transform-fade-down">
    <div
      v-if="profile"
      class="text-left bg-white py-1 mt-2 rounded-md shadow-xs absolute right-6 lg:right-28 z-30 ring-1 ring-gray-300"
      :class="width"
    >
      <nuxt-link
        to="/siswa/dashboard/profile"
        class="w-full block text-left px-4 py-2 text-sm leading-5 text-gray-700 transition duration-150 ease-in-out hover:bg-gray-100 focus:outline-none focus:bg-gray-100"
        role="menuitem"
      >
        Profile
      </nuxt-link>
      <nuxt-link
        v-if="$nuxt.$route.path.includes('dashboard')"
        to="/"
        class="w-full block text-left px-4 py-2 text-sm leading-5 text-gray-700 transition duration-150 ease-in-out hover:bg-gray-100 focus:outline-none focus:bg-gray-100"
        role="menuitem"
      >
        Home
      </nuxt-link>
      <nuxt-link
        v-else
        to="siswa/dashboard"
        class="w-full block text-left px-4 py-2 text-sm leading-5 text-gray-700 transition duration-150 ease-in-out hover:bg-gray-100 focus:outline-none focus:bg-gray-100"
        role="menuitem"
      >
        Dashboard
      </nuxt-link>
      <hr class="w-full bg-gray-400" />
      <button
        class="w-full block text-left px-4 py-2 text-sm leading-5 text-gray-700 transition duration-150 ease-in-out hover:bg-gray-100 focus:outline-none focus:bg-gray-100 space-x-1 flex items-center"
        role="menuitem"
        @click="logout"
      >
        <span> Sign out </span>
      </button>
    </div>
  </transition>
</template>

<script>
export default {
  props: {
    profile: {
      type: Boolean,
      required: true,
    },
    width: {
      type: String,
      required: true,
    },
  },
  data() {
    return {
      token: this.$auth.strategy.token.get(),
    }
  },
  computed: {
    user() {
      return this.$auth.user
    },
  },
  methods: {
    async logout() {
      try {
        await this.$auth.logout()
      } catch (err) {}
    },
  },
}
</script>
