<template>
  <section class="text-gray-800 bg-blue-100 body-font">
    <div class="container mx-auto flex px-5 py-24 md:flex-row flex-col items-center">
      <div class="lg:flex-grow md:w-1/2 lg:pr-24 md:pr-16 flex flex-col md:items-start md:text-left mb-16 md:mb-0 items-center text-center">
        <h1 class="title-font sm:text-4xl text-3xl mb-4 font-medium text-gray-900">Kenneth Reyes Heredia</h1>
        <p class="mb-8 leading-relaxed">{{intro}}</p>
        <div class="flex justify-center">
          <button class="inline-flex text-white bg-indigo-500 border-0 py-2 px-6 focus:outline-none hover:bg-indigo-600 rounded text-lg" >
            <a href="mailto:kennethreyesheredia@gmail.com">Email</a>
          </button>

        </div>
      </div>
      <div class="lg:max-w-lg lg:w-full md:w-1/2 w-5/6">
        <img class="object-cover object-center rounded" alt="hero" src="../assets/dev.png">
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: "Hero",
  data() {
    return {
      intro: "A developer with 6 years of hand on experience in both frontend and backend development, mobile, devops, data analysis, and project management."
    }
  },
}
</script>

<style scoped>

</style>