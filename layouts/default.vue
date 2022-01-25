<template>
  <div class="min-h-screen bg-gray-100">
    <UserNavbar />
    <div class="flex">
      <UserSidebar />

      <main>
        <Nuxt />
      </main>
    </div>
    <UserFooter />
  </div>
</template>

<script>
export default {
  name: 'DefaultLayout',
}
</script>
