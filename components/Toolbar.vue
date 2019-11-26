<template>
  <div class="container">
    <nav class="flex items-center justify-between flex-wrap bg-transparent p-6">
      <div class="flex items-center flex-shrink-0 text-white mr-6">
        <img src="~/assets/images/fifa20.svg" alt width="250px" height="100px" />
      </div>
      <div class="block lg:hidden">
        <button
          class="flex items-center px-3 py-2 border rounded text-teal-200 border-teal-400 hover:text-white hover:border-white"
        >
          <svg class="fill-current h-3 w-3" viewBox="0 0 20 20" xmlns="http://www.w3.org/2000/svg">
            <title>Menu</title>
            <path d="M0 3h20v2H0V3zm0 6h20v2H0V9zm0 6h20v2H0v-2z" />
          </svg>
        </button>
      </div>
      <div class="w-full block flex-grow lg:flex lg:items-center lg:w-auto">
        <div class="text-sm lg:flex-grow">
          
        </div>
        <div>
          <a
            href="#responsive-header"
            class="block mt-4 lg:inline-block text-lg lg:mt-0 text-black hover:text-red-500 mr-4"
          >Weeks</a>

          <a
            href="#responsive-header"
            class="block mt-4 lg:inline-block text-lg lg:mt-0 text-black hover:text-red-500 mr-4"
          >Dashboard</a>
        </div>
      </div>
    </nav>
  </div>
</template>

<script>
export default {

}
</script>

<style scoped>
.container {
  margin: 0 auto;
}
</style>