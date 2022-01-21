<template>
  <div>
    <nav class="text-sm font-semibold mb-6" aria-label="Breadcrumb">
      <ol class="list-none p-0 inline-flex">
        <li class="flex items-center text-blue-500">
          <a href="#" class="text-gray-700">Home</a>
          <svg
            class="fill-current w-3 h-3 mx-3"
            xmlns="http://www.w3.org/2000/svg"
            viewBox="0 0 320 512"
          >
            <path
              d="M285.476 272.971L91.132 467.314c-9.373 9.373-24.569 9.373-33.941 0l-22.667-22.667c-9.357-9.357-9.375-24.522-.04-33.901L188.505 256 34.484 101.255c-9.335-9.379-9.317-24.544.04-33.901l22.667-22.667c9.373-9.373 24.569-9.373 33.941 0L285.475 239.03c9.373 9.372 9.373 24.568.001 33.941z"
            />
          </svg>
        </li>
        <li class="flex items-center">
          <a href="#" class="text-gray-600">Dashboard</a>
        </li>
      </ol>
    </nav>
    <!-- breadcrumb end -->

    <div class="lg:flex justify-between items-center mb-6">
      <p class="text-2xl font-semibold mb-2 lg:mb-0">Selamat Datang, Tiara!</p>
    </div>

    <div class="flex flex-wrap -mx-3 mb-20">
      <div class="w-1/2 xl:w-1/4 px-3">
        <div
          class="w-full bg-white border text-blue-400 rounded-lg flex items-center p-6 mb-6 xl:mb-0"
        >
          <svg
            xmlns="http://www.w3.org/2000/svg"
            class="h-10 w-10"
            fill="none"
            viewBox="0 0 24 24"
            stroke="currentColor"
          >
            <path d="M12 14l9-5-9-5-9 5 9 5z" />
            <path
              d="M12 14l6.16-3.422a12.083 12.083 0 01.665 6.479A11.952 11.952 0 0012 20.055a11.952 11.952 0 00-6.824-2.998 12.078 12.078 0 01.665-6.479L12 14z"
            />
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-width="2"
              d="M12 14l9-5-9-5-9 5 9 5zm0 0l6.16-3.422a12.083 12.083 0 01.665 6.479A11.952 11.952 0 0012 20.055a11.952 11.952 0 00-6.824-2.998 12.078 12.078 0 01.665-6.479L12 14zm-4 6v-7.5l4-2.222"
            />
          </svg>

          <div class="pl-3 text-gray-700">
            <p class="font-semibold text-3xl">157</p>
            <p>Siswa</p>
          </div>
        </div>
      </div>

      <div class="w-1/2 xl:w-1/4 px-3">
        <div
          class="w-full bg-white border text-blue-400 rounded-lg flex items-center p-6 mb-6 xl:mb-0"
        >
          <svg
            xmlns="http://www.w3.org/2000/svg"
            class="h-10 w-10"
            fill="none"
            viewBox="0 0 24 24"
            stroke="currentColor"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-width="2"
              d="M8 14v3m4-3v3m4-3v3M3 21h18M3 10h18M3 7l9-4 9 4M4 10h16v11H4V10z"
            />
          </svg>

          <div class="pl-3 text-gray-700">
            <p class="font-semibold text-3xl">12</p>
            <p>Kelas</p>
          </div>
        </div>
      </div>

      <div class="w-1/2 xl:w-1/4 px-3">
        <div
          class="w-full bg-white border text-blue-400 rounded-lg flex items-center p-6"
        >
          <svg
            xmlns="http://www.w3.org/2000/svg"
            class="h-10 w-10"
            fill="none"
            viewBox="0 0 24 24"
            stroke="currentColor"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-width="2"
              d="M19 20H5a2 2 0 01-2-2V6a2 2 0 012-2h10a2 2 0 012 2v1m2 13a2 2 0 01-2-2V7m2 13a2 2 0 002-2V9a2 2 0 00-2-2h-2m-4-3H9M7 16h6M7 8h6v4H7V8z"
            />
          </svg>

          <div class="pl-3 text-gray-700">
            <p class="font-semibold text-3xl">31</p>
            <p>Materi</p>
          </div>
        </div>
      </div>

      <div class="w-1/2 xl:w-1/4 px-3">
        <div
          class="w-full bg-white border text-blue-400 rounded-lg flex items-center p-6"
        >
          <svg
            xmlns="http://www.w3.org/2000/svg"
            class="h-10 w-10"
            fill="none"
            viewBox="0 0 24 24"
            stroke="currentColor"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-width="2"
              d="M12 6.253v13m0-13C10.832 5.477 9.246 5 7.5 5S4.168 5.477 3 6.253v13C4.168 18.477 5.754 18 7.5 18s3.332.477 4.5 1.253m0-13C13.168 5.477 14.754 5 16.5 5c1.747 0 3.332.477 4.5 1.253v13C19.832 18.477 18.247 18 16.5 18c-1.746 0-3.332.477-4.5 1.253"
            />
          </svg>

          <div class="pl-3 text-gray-700">
            <p class="font-semibold text-3xl">107</p>
            <p>Tugas Siswa</p>
          </div>
        </div>
      </div>
    </div>

    <div class="flex flex-wrap -mx-3">
      <div class="w-full xl:w-1/3 px-3">
        <p class="text-xl font-semibold mb-4">Recent Sales</p>

        <div class="w-full bg-white border rounded-lg p-4 mb-8 xl:mb-0">
          <canvas id="buyers-chart" width="600" height="400"></canvas>
        </div>
      </div>

      <div class="w-full xl:w-1/3 px-3">
        <p class="text-xl font-semibold mb-4">Pendaftar</p>

        <div class="w-full bg-white border rounded-lg p-4 mb-8 xl:mb-0">
          <canvas id="reviews-chart" width="600" height="400"></canvas>
        </div>
      </div>

      <div class="w-full xl:w-1/3 px-3">
        <p class="text-xl font-semibold mb-4">Recent Transactions</p>
        <div class="w-full bg-white border rounded-lg p-4">
          <div
            class="w-full bg-gray-100 border rounded-lg flex justify-between items-center px-4 py-2 mb-4"
          >
            <div>
              <p class="font-semibold text-xl">Trent Murphy</p>
              <p>Product 1</p>
            </div>
            <span class="text-green-500 font-semibold text-lg">$25.00</span>
          </div>

          <div
            class="w-full bg-gray-100 border rounded-lg flex justify-between items-center px-4 py-2 mb-4"
          >
            <div>
              <p class="font-semibold text-xl">Joseph Brent</p>
              <p>Product 34</p>
            </div>
            <span class="text-red-500 font-semibold text-lg">$74.99</span>
          </div>

          <div
            class="w-full bg-gray-100 border rounded-lg flex justify-between items-center px-4 py-2 mb-4"
          >
            <div>
              <p class="font-semibold text-xl">Jacob Bator</p>
              <p>Product 23</p>
            </div>
            <span class="text-green-500 font-semibold text-lg">$14.95</span>
          </div>

          <div
            class="w-full bg-gray-100 border rounded-lg flex justify-between items-center px-4 py-2"
          >
            <div>
              <p class="font-semibold text-xl">Alex Mason</p>
              <p>Product 66</p>
            </div>
            <span class="text-green-500 font-semibold text-lg">$44.99</span>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  layout: 'dashboard.vue',
}
</script>
