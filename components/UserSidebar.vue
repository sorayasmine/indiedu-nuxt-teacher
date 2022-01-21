<template>
  <!-- give the sidebar z-50 class so its higher than the navbar if you want to see the logo -->
  <!-- you will need to add a little "X" button next to the logo in order to close it though -->
  <div
    id="main-nav"
    class="min-h-full px-3 py-3 space-y-1 w-80 fixed h-screen bg-white border-r"
  >
    <div class="w-full h-20 border-b flex px-4 items-center mb-8">
      <logo />
    </div>

    <div class="divide-y divide-gray-200 px-4">
      <ul class="pb-4 space-y-1 text-base">
        <li>
          <NuxtLink
            :to="{ name: 'dashboard-user' }"
            class="flex items-center p-2 space-x-4 rounded-md font-medium hover:bg-gray-100 hover:text-primary"
          >
            <svg
              xmlns="http://www.w3.org/2000/svg"
              class="h-6 w-6 fill-current"
              viewBox="0 0 20 20"
              fill="currentColor"
            >
              <path
                d="M3 4a1 1 0 011-1h12a1 1 0 011 1v2a1 1 0 01-1 1H4a1 1 0 01-1-1V4zM3 10a1 1 0 011-1h6a1 1 0 011 1v6a1 1 0 01-1 1H4a1 1 0 01-1-1v-6zM14 9a1 1 0 00-1 1v6a1 1 0 001 1h2a1 1 0 001-1v-6a1 1 0 00-1-1h-2z"
              />
            </svg>
            <span>Dashboard</span>
          </NuxtLink>
        </li>
        <li>
          <NuxtLink
            :to="{ name: 'dashboard-siswa' }"
            class="flex items-center p-2 space-x-4 rounded-md font-medium hover:bg-gray-100 hover:text-primary"
          >
            <svg
              xmlns="http://www.w3.org/2000/svg"
              class="h-6 w-6 fill-current"
              viewBox="0 0 20 20"
              fill="currentColor"
            >
              <path
                d="M3 4a1 1 0 011-1h12a1 1 0 011 1v2a1 1 0 01-1 1H4a1 1 0 01-1-1V4zM3 10a1 1 0 011-1h6a1 1 0 011 1v6a1 1 0 01-1 1H4a1 1 0 01-1-1v-6zM14 9a1 1 0 00-1 1v6a1 1 0 001 1h2a1 1 0 001-1v-6a1 1 0 00-1-1h-2z"
              />
            </svg>
            <span>Kelas</span>
          </NuxtLink>
        </li>
        <li>
          <NuxtLink
            :to="{ name: 'dashboard-siswa-pelajaran-terakhir' }"
            class="flex items-center p-2 space-x-4 rounded-md font-medium hover:bg-gray-100 hover:text-primary transition duration-200"
          >
            <svg
              xmlns="http://www.w3.org/2000/svg"
              class="h-6 w-6"
              viewBox="0 0 20 20"
              fill="currentColor"
            >
              <path
                fill-rule="evenodd"
                d="M18 13V5a2 2 0 00-2-2H4a2 2 0 00-2 2v8a2 2 0 002 2h3l3 3 3-3h3a2 2 0 002-2zM5 7a1 1 0 011-1h8a1 1 0 110 2H6a1 1 0 01-1-1zm1 3a1 1 0 100 2h3a1 1 0 100-2H6z"
                clip-rule="evenodd"
              />
            </svg>
            <span>Materi</span>
          </NuxtLink>
        </li>
        <li>
          <NuxtLink
            to="/KelasSiswa"
            class="flex items-center p-2 space-x-4 rounded-md font-medium hover:bg-gray-100 hover:text-primary transition duration-200"
          >
            <svg
              xmlns="http://www.w3.org/2000/svg"
              class="h-6 w-6"
              viewBox="0 0 20 20"
              fill="currentColor"
            >
              <path
                d="M9 6a3 3 0 11-6 0 3 3 0 016 0zM17 6a3 3 0 11-6 0 3 3 0 016 0zM12.93 17c.046-.327.07-.66.07-1a6.97 6.97 0 00-1.5-4.33A5 5 0 0119 16v1h-6.07zM6 11a5 5 0 015 5v1H1v-1a5 5 0 015-5z"
              />
            </svg>
            <span>Siswa</span>
          </NuxtLink>
        </li>
        <li class="border-b pb-4">
          <NuxtLink
            :to="{ name: 'dashboard-siswa-transaction' }"
            class="flex items-center p-2 space-x-4 rounded-md font-medium hover:bg-gray-100 hover:text-primary transition duration-200"
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
                d="M3 10h18M7 15h1m4 0h1m-7 4h12a3 3 0 003-3V8a3 3 0 00-3-3H6a3 3 0 00-3 3v8a3 3 0 003 3z"
              />
            </svg>
            <span>Tugas Siswa</span>
          </NuxtLink>
        </li>
      </ul>
      <ul class="pb-2 space-y-1 text-base">
        <li
          class="text-gray-500 font-medium hover:bg-gray-100 hover:text-primary transition duration-200"
        >
          <NuxtLink
            :to="{ name: 'dashboard-siswa-profile' }"
            class="flex items-center p-2 space-x-4 rounded-md"
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
                d="M5.121 17.804A13.937 13.937 0 0112 16c2.5 0 4.847.655 6.879 1.804M15 10a3 3 0 11-6 0 3 3 0 016 0zm6 2a9 9 0 11-18 0 9 9 0 0118 0z"
              />
            </svg>
            <span>Profil</span>
          </NuxtLink>
        </li>
        <li
          class="text-gray-500 font-medium hover:bg-gray-100 hover:text-primary transition duration-200"
        >
          <NuxtLink
            :to="{ name: 'dashboard-siswa-notification' }"
            class="flex items-center p-2 space-x-4 rounded-md"
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
                d="M15 17h5l-1.405-1.405A2.032 2.032 0 0118 14.158V11a6.002 6.002 0 00-4-5.659V5a2 2 0 10-4 0v.341C7.67 6.165 6 8.388 6 11v3.159c0 .538-.214 1.055-.595 1.436L4 17h5m6 0v1a3 3 0 11-6 0v-1m6 0H9"
              />
            </svg>
            <span>Notifikasi</span>
          </NuxtLink>
        </li>
        <li
          class="text-gray-500 font-medium hover:bg-gray-100 hover:text-primary transition duration-200"
        >
          <button
            class="flex items-center p-2 space-x-4 rounded-md"
            @click="logout"
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
                d="M17 16l4-4m0 0l-4-4m4 4H7m6 4v1a3 3 0 01-3 3H6a3 3 0 01-3-3V7a3 3 0 013-3h4a3 3 0 013 3v1"
              />
            </svg>
            <span>Log Out</span>
          </button>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
import { mapGetters, mapMutations } from 'vuex'
import Logo from './partials/Logo.vue'

export default {
  components: { Logo },
  computed: {
    ...mapGetters({ drawer: 'drawer/getDrawerState' }),
  },
  methods: {
    ...mapMutations({ toggle: 'drawer/toggle' }),
  },
}
</script>
