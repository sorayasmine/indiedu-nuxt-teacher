<template>
  <div class="w-full px-20 py-10">
    <div class="mx-auto w-full bg-white">
      <form @submit.prevent="createData">
        <input
          id="name"
          v-model.number="name"
          type="text"
          placeholder="Nama Kategori"
        />
        <button
          v-show="!updateSubmit"
          type="submit"
          class="block text-white bg-blue-700 hover:bg-blue-800 focus:ring-4 focus:ring-blue-300 font-medium rounded-lg text-sm px-5 py-2.5 text-center dark:bg-blue-600 dark:hover:bg-blue-700 dark:focus:ring-blue-800"
        >
          Tambah Data
        </button>
        <button
          v-show="updateSubmit"
          type="button"
          class="block text-white bg-blue-700 hover:bg-blue-800 focus:ring-4 focus:ring-blue-300 font-medium rounded-lg text-sm px-5 py-2.5 text-center dark:bg-blue-600 dark:hover:bg-blue-700 dark:focus:ring-blue-800"
          @click="updateData()"
        >
          Ubah Data
        </button>
      </form>

      <div class="">
        <table class="table-auto">
          <thead class="border-2">
            <tr>
              <th>No</th>
              <th>Kategori</th>
              <th>Action</th>
            </tr>
          </thead>

          <tbody>
            <tr v-for="(category, index) in categories" :key="index">
              <td>{{ index + 1 }}</td>
              <td>{{ category.name }}</td>
              <td class="flex">
                <button
                  class="block text-white bg-red-600"
                  @click="deleteData(category.id)"
                >
                  Delete
                </button>
                <button
                  class="block text-white bg-yellow-300"
                  @click="editData(category)"
                >
                  Edit
                </button>
              </td>
            </tr>
          </tbody>
        </table>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      categories: [],
      name: '',
      updateSubmit: false,
    }
  },
  mounted() {
    this.showData()
  },
  methods: {
    async showData() {
      try {
        const { data } = await this.$axios.$get('/category', {
          headers: {
            Authorization: 'Bearer ' + this.$auth.strategy.token.get(),
          },
        })
        this.categories = data
        console.log(data)
      } catch ({ data }) {
        console.log(data)
      }
    },
    async createData() {
      try {
        await this.$axios.$post(
          `/category`,

          {
            name: this.name,
            type: this.type,
          },
          {
            headers: {
              Authorization: 'Bearer ' + this.$auth.strategy.token.get(),
            },
          }
        )
        this.showData()
      } catch ({ response }) {
        console.log(response.data)
      }
    },
    async deleteData(id) {
      try {
        const data = await this.$axios.$delete(`/category/${id}`)
        this.categories.splice(id)
        this.showData()
        console.log(data)
      } catch (err) {
        console.error(err)
      }
    },
    editData(category) {
      this.updateSubmit = true
      this.id = category.id
      this.name = category.name
      this.type = category.type
    },
    async updateData() {
      try {
        await this.$axios.$post(`/category/${this.id}`, {
          name: this.name,
        })
        this.updateSubmit = false
        this.showData()
      } catch (response) {
        console.log(response.data)
      }
    },
  },
}
</script>
