<template>
  <nav class="w-full flex justify-between bg-white">
    <div class="space-y-2">
      <h2 class="text-2xl font-bold leading-tight text-primaryText">
        <slot name="header"></slot>
      </h2>
      <p class="text-secondaryText">
        <slot name="subheader"></slot>
      </p>
    </div>
    <div>
      <div class="cursor-pointer">
        <div class="flex items-center" @click="profile = !profile">
          <div
            class="px-3 py-1 bg-secondary text-lg font-semibold uppercase text-white rounded-full"
          >
            {{ firstLetterUser }}
          </div>
          <svg
            xmlns="http://www.w3.org/2000/svg"
            class="h-4 xl:h-5 w-4 xl:w-5 mt-1"
            viewBox="0 0 20 20"
            fill="currentColor"
          >
            <path
              fill-rule="evenodd"
              d="M5.293 7.293a1 1 0 011.414 0L10 10.586l3.293-3.293a1 1 0 111.414 1.414l-4 4a1 1 0 01-1.414 0l-4-4a1 1 0 010-1.414z"
              clip-rule="evenodd"
            />
          </svg>
        </div>
        <dropdown-menu :profile="profile" width="w-36"></dropdown-menu>
      </div>
    </div>
  </nav>
</template>

<script>
import DropdownMenu from '@/components/partials/DropdownMenu.vue'

export default {
  components: {
    DropdownMenu,
  },
  data() {
    return {
      profile: false,
    }
  },
  computed: {
    firstLetterUser() {
      if (this.$auth.loggedIn) {
        return this.$store.state.auth.user.name.charAt(0)
      } else {
        return 'A'
      }
    },
  },
  mounted() {
    document.addEventListener('click', this.close)
  },
  beforeDestroy() {
    document.removeEventListener('click', this.close)
  },
  methods: {
    close(e) {
      if (!this.$el.contains(e.target)) {
        this.dropdown = false
        this.profile = false
      }
    },
  },
}
</script>
