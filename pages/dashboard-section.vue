<template>
  <div class="w-full px-20 py-10">
    <div class="mx-auto bg-white">
      <form class="grid" @submit.prevent="createData">
        <input
          id="title"
          v-model="title"
          type="text"
          class=""
          placeholder="Judul"
        />
        <input
          id="description"
          v-model="description"
          type="text"
          placeholder="Deskripsi"
        />
        <input
          id="cover"
          v-model="cover"
          type="text"
          class=""
          placeholder="Cover"
        />
        <input id="price" v-model="price" type="text" placeholder="Price" />
        <input id="status" v-model="status" type="text" placeholder="status" />
        <input
          id="grade_id"
          v-model="grade_id"
          type="text"
          placeholder="Price"
        />
        <input
          id="subject_category_id"
          v-model="subject_category_id"
          type="text"
          placeholder="status"
        />
        <button
          v-show="!updateSubmit"
          type="submit"
          class="block w-2/12 text-white bg-blue-700 hover:bg-blue-800 focus:ring-4 focus:ring-blue-300 font-medium rounded-lg text-sm px-5 py-2.5 text-center dark:bg-blue-600 dark:hover:bg-blue-700 dark:focus:ring-blue-800"
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
              <th>Judul</th>
              <th>Deskripsi</th>
              <th>Cover</th>
              <th>Price</th>
              <th>Status</th>
              <th>Grade_id</th>
              <th>subject_category_id</th>
              <th>Action</th>
            </tr>
          </thead>

          <tbody>
            <tr v-for="(subject, index) in subjects" :key="index">
              <td>{{ index + 1 }}</td>
              <td>{{ subject.title }}</td>
              <td>{{ subject.description }}</td>
              <td>{{ subject.cover }}</td>
              <td>{{ subject.price }}</td>
              <td>{{ subject.status }}</td>
              <td>{{ subject.grade_id }}</td>
              <td>{{ subject.subject_category_id }}</td>
              <td class="flex m-3">
                <button
                  class="block text-white bg-red-600"
                  @click="deleteData(subject.id)"
                >
                  Delete
                </button>
                <button
                  class="block text-white bg-yellow-300"
                  @click="editData(subject)"
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
      subjects: [],
      title: '',
      description: '',
      cover: '',
      price: '',
      status: '',
      grade_id: '',
      subject_category_id: '',
      updateSubmit: false,
    }
  },
  fetch() {
    this.showData()
  },
  methods: {
    async showData() {
      try {
        const { data } = await this.$axios.$get('/subject', {
          headers: {
            Authorization: 'Bearer ' + this.$auth.strategy.token.get(),
          },
        })
        this.subjects = data
        console.log(data)
      } catch ({ data }) {
        console.log(data)
      }
    },
    async createData() {
      try {
        await this.$axios.$post(
          `/subject`,

          {
            title: this.title,
            description: this.description,
            cover: this.cover,
            slug: this.slug,
            price: this.price,
            status: this.status,
            grade_id: this.grade_id,
            subject_category_id: this.subject_category_id,
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
        const data = await this.$axios.$delete(`/subject/${id}`)
        this.subjects.splice(id)
        this.showData()
        console.log(data)
      } catch (err) {
        console.error(err)
      }
    },
    editData(subject) {
      this.updateSubmit = true
      this.id = subject.id
      this.name = subject.name
      this.type = subject.type
    },
    async updateData() {
      try {
        await this.$axios.$post(`/subject/${this.id}`, {
          name: this.name,
          type: this.type,
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
