<template>
  <div class="w-full px-20 py-10">
    <div class="mx-auto w-full bg-white">
      <!-- Modal toggle -->
      <button
        class="block text-white bg-blue-700 hover:bg-blue-800 focus:ring-4 focus:ring-blue-300 font-medium rounded-lg text-sm px-5 py-2.5 text-center dark:bg-blue-600 dark:hover:bg-blue-700 dark:focus:ring-blue-800"
        type="button"
        data-modal-toggle="defaultModal"
      >
        Toggle modal
      </button>

      <!-- Main modal -->

      <div class="">
        <table class="table-auto">
          <thead class="border-2">
            <tr>
              <th>No</th>
              <th>Kelas</th>
              <th>Tipe</th>
              <th>Action</th>
            </tr>
          </thead>

          <tbody>
            <tr v-for="(grade, index) in grades" :key="index">
              <td>{{ index + 1 }}</td>
              <td>{{ grade.name }}</td>
              <td>{{ grade.type }}</td>
              <td class="flex">
                <button class="block" @click="deleteData(grade.id)">
                  Delete
                </button>
                <button class="block">Edit</button>
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
      grades: [],
      name: '',
      type: '',
    }
  },
  mounted() {
    this.showData()
  },
  methods: {
    async showData() {
      try {
        // console.log(this.$auth.strategy.token.get())
        const { data } = await this.$axios.$get('/grade', {
          headers: {
            Authorization: 'Bearer ' + this.$auth.strategy.token.get(),
          },
        })
        this.grades = data
        console.log(data)
      } catch ({ data }) {
        console.log(data)
      }
    },
    async createData() {
      try {
        // console.log(this.$auth.strategy.token.get())
        const { data } = await this.$axios.$post('/grade', {
          data: {
            name: this.name,
            type: this.type,
          },
        })
        this.grades = data
        console.log(data)
      } catch ({ data }) {
        console.log(data)
      }
    },
    async deleteData(id) {
      try {
        const data = await this.$axios.$delete(`/grade/${id}`)
        this.grades.splice(id)
        // this.grades = data
        console.log(data)
      } catch (err) {
        console.error(err)
      }
    },
    async updateData() {},
  },
}
</script>
