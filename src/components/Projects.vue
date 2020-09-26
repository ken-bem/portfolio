<template>
  <section class="text-gray-700 body-font" id="projects">
    <div class="container px-5 py-24 mx-auto">
      <div class="flex flex-wrap w-full mb-20">
        <div class="lg:w-1/2 w-full mb-6 lg:mb-0">
          <h1 class="sm:text-3xl text-2xl font-medium title-font mb-2 text-gray-900">Projects</h1>
          <div class="h-1 w-20 bg-indigo-500 rounded"></div>
        </div>
        <p class="lg:w-1/2 w-full leading-relaxed text-lg text-center">{{intro}}</p>
      </div>
      <div class="flex flex-wrap -m-4">
        <div class="xl:w-1/4 md:w-1/2 p-4" v-for="project in projects" :key="project.name">
          <div class="bg-gray-100 p-6 rounded-lg">
            <img class="h-40 rounded w-full object-contain object-center mb-6" :src="project.image" alt="content">
            <h3 class="tracking-widest text-indigo-500 text-xs font-medium title-font">
              <a target="_blank" :href="project.live" v-if="project.live" class="text-xs font-semibold inline-block py-1 px-2 uppercase rounded text-indigo-600 bg-indigo-200 uppercase last:mr-0 mr-1">View Live</a>
              <a target="_blank" :href="project.code" v-if="project.code" class="text-xs font-semibold inline-block py-1 px-2 uppercase rounded text-indigo-600 bg-indigo-200 uppercase last:mr-0 mr-1" >View Code</a>
            </h3>
            <h2 class="text-lg text-gray-900 font-medium title-font mb-4">{{project.name}}</h2>
            <p :key="tag" v-for="tag in project.tags" class="leading-relaxed text-base">{{tag}}</p>
          </div>
        </div>

      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: "Projects",
  data() {
    return {
      intro: "A sample of some of the projects I have done over the years.",
      projects: [
        {
          name: "PR Ticket",
          tags: ["PHP", "Frontend", "Rest API"],
          live: "https://prticket.com",
          image: require('../assets/prticket.png'),
          code: false,

        },
        {
          name: "Quote SMS",
          tags: ["Spring Boot", "Java", "Twilio"],
          live: false,
          image: require('../assets/twilio.png'),
          code: "https://github.com/ken-bem/sms"
        },
        {
          name: "Portfolio",
          tags: ["Vue", "Tailwind"],
          live: "https://portfolio.foocases.com",
          code: "https://github.com/ken-bem/portfolio",
          image: require('../assets/portfolio.png'),
        },
        {
          name: "Primavera",
          tags: ["Spring Boot", "Java", "Mysql", "Templates"],
          live: false,
          image: require('../assets/spring.png'),
          code: "https://github.com/ken-bem/primavera"
        },

      ],
    }
  },
}
</script>

<style scoped>

</style>