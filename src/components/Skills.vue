<template>
  <section class="text-white body-font bg-gray-900">
    <div class="container px-5 py-24 mx-auto">
      <div class="flex flex-wrap w-full mb-20 flex-col items-center text-center">
        <h1 class="sm:text-3xl text-2xl font-medium title-font mb-2 ">Skills</h1>
        <p class="lg:w-1/2 w-full leading-relaxed text-base">These are my tools of the trade.</p>
      </div>
      <div class="flex flex-wrap -m-4">
        <div class="xl:w-1/3 md:w-1/2 p-4" v-for="skill in skills">
          <div class="border border-gray-300 p-6 rounded-lg">
            <div class="w-10 h-10 inline-flex items-center justify-center rounded-full bg-indigo-100 text-indigo-500 mb-4">
              <svg fill="none" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" class="w-6 h-6" viewBox="0 0 24 24">
                <path d="M22 12h-4l-3 9L9 3l-3 9H2"></path>
              </svg>
            </div>
            <h2 class="text-lg text-white font-medium title-font mb-2">{{skill.name}}</h2>
            <div>
                <Label :key="index"  :tag="tag"  v-for="(tag, index) in skill.tags" />
            </div>
          </div>
        </div>
      </div>
      <button class="flex mx-auto mt-16 text-white bg-indigo-500 border-0 py-2 px-8 focus:outline-none hover:bg-indigo-600 rounded text-lg">
        <a href="mailto:kennethreyesheredia@gmail.com">Email</a>
      </button>
    </div>
  </section>
</template>

<script>
import Label from "@/components/Label";
export default {
  name: "Skills",
  components: {Label},
  data() {
    return {
      skills:[
        {
          name: "Frontend",
          tags: ["HTML", "CSS", "SASS", "SCSS", "JavaScript", "ES6", "Vue", "React", "Yarn", "Webpack"]
        },
        {
          name: "Backend",
          tags: ["Java", "Spring Boot", "Hibernate", "JPA", "Kafka", "Netflix OSS", "Python", "Django", "PHP", "Laravel"]
        },
        {
          name: "Database",
          tags: ["Mysql", "MongoDb", "Postgres"]
        },
        {
          name: "Apps",
          tags: [
              "Photoshop: Beginner", "Illustrator: Beginner", "Azure DevOps"

          ]
        },
        {
          name: "Other",
          tags: ["Git", "Github", "Elasticsearch", "GraphQL",
            "Rest API", "WordPress", "Lombok", "Data Analysis", "AWS",
            "Digital Ocean", "Google APIS", "Mapbox", "Twilio", "Facebook Business SDK", "Docker"]
        },
        {
          name: "Language",
          tags: ["English: Native", "Spanish: Native", "French: A2"]
        }
      ],
    }
  },
}
</script>

<style scoped>

</style>