<template>
  <div id="app" class="antialiased h-screen" @keydown.esc="isOpen = false">
    <div class="bg-indigo-800 lg:h-full p-4">
      <div class="align-middle flex flex-wrap justify-between text-white font-black ">
        <div class="sm:text-center m">
          <a href="/" class="font-black text-2xl ">Foocases</a>
        </div>
        <div class="hidden md:block">
          <ul class="flex flex-wrap justify-between items-center menu h-full ">

            <li class="mx-4">
              <a @click="scrollMeTo('projects')">Projects</a>
            </li>
            <li class="mx-4 relative">
              <div class="">
                <button class="font-black" @click="isOpen = !isOpen">Contact &darr;</button>
              </div>
              <button v-if="isOpen"

                      @click="isOpen = false" tabindex="-1"
                      class="fixed top-0 left-0 right-0 bottom-0 bg-black opacity-50  w-full h-full"></button>
              <div v-if="isOpen" class="bg-white rounded-lg py-2 text-gray-900 w-32 mt-2 shadow-lg absolute right-0">
                <a :href="links.email" class="block py-2 px-4 hover:bg-blue-800 hover:text-white">Email</a>
                <a :href="links.linkedIn" class="block py-2 px-4 hover:bg-blue-800 hover:text-white">LinkedIn</a>
                <a :href="links.github" class="block py-2 px-4 hover:bg-blue-800 hover:text-white">Github</a>
              </div>
            </li>
          </ul>
        </div>
      </div>

      <div class="flex flex-wrap p-4 items-center justify-between md:h-full w-full">
        <div class="md:w-1/2 w-full">
          <h3 class="md:text-4xl text-2xl text-white border-b-4 mb-8">Kenneth Reyes Heredia</h3>
          <h3 class="text-2xl text-white my-2">Full stack developer</h3>
          <p class="text-white mt-4 font-bold">
            A developer with 4 years of hand on experience in both frontend and backend development, devop, data analysis and project management.
          </p>
          <div class="font-black mt-16 flex flex-wrap ">
            <a :href="links.email" class="block m-2  bg-white px-4 py-2">Email</a>
            <a :href="links.github" class="block m-2  bg-white px-4 py-2">Github</a>
            <a :href="links.linkedIn" class="block m-2  bg-white px-4 py-2">LinkedIn</a>
          </div>
        </div>
        <div class="hidden md:block md:w-1/2 md:items-center align-baseline ">
          <img src="./assets/dev.png" class="p-16 ">
        </div>
      </div>

    </div>
    <div class="bg-gray-200 h-auto p-4" ref="projects">
        <div class="px-4 pt-4">
            <p class="text-2xl uppercase">Projects</p>
        </div>
        <div class="px-4">
            <div class="row">
                <div v-for="( project, index) in projects"
                     :key="index"
                     class="col-xs-12 col-sm-8 col-md-6 col-lg-4 mt-3">
                  <div class="p-4 mx-2 bg-white shadow rounded">
                      <div class="">
                          <img :src="project.image" class="h-32 w-full object-cover">
                      </div>
                      <div class="flex-wrap flex mt-2">
                          <span class="bg-blue-200 px-2 mr-3 text-blue-900 text-sm"
                                v-for="(tag, index) in project.tags"
                                :key="index">{{tag}}</span>
                      </div>
                      <div>
                          <p class="text-2xl uppercase leading-loose">{{project.name}}</p>
                      </div>
                      <div class="flex justify-around">
                          <a
                                  target="_blank"
                                  class="bg-teal-300 px-2  text-white font-black"
                                  :href="project.live">
                              {{project.live ? "Live":"Code Only"}}
                          </a>
                          <a
                                  target="_blank"
                                  :href="project.code === false ? '#' : project.code">
                            {{!project.code ? 'Private Code' : "Source"}}
                          </a>
                      </div>
                  </div>
                </div>
            </div>
        </div>
    </div>
    <div id="skills" class="p-4" ref="skills">
      <div class="px-4 pt-4">
        <p class="text-2xl uppercase">Skills</p>
      </div>
      <div class="row">
          <div class=" col-lg-3 col-xs-12  mt-1 " v-for="(skill, index) in skills" :key="index">

              <div class="p-4  text-center border-2 h-64">
                  <div class="px-8 text-center">
                      <h2 class="font-black text-xl">{{skill.name}}</h2>
                  </div>
                  <div class=" text-center">
                    <span v-for="(tag, index) in skill.tags"
                      :key="index"
                      class="ml-2">
                        <span v-if="index>0">&bullet;</span> {{tag}}
                    </span>
                  </div>
              </div>
          </div>
      </div>
    </div>
  </div>
</template>

<script>

export default {
  name: 'app',
  methods: {
    scrollMeTo(refName) {
      let element = this.$refs[refName];
      let top = element.offsetTop;

      window.scrollTo({top: top, behavior: 'smooth'});
    }
  },
  data() {
    return {
      isOpen: false,
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
      projects: [
        {
          name: "PR Ticket",
          tags: ["PHP", "Frontend", "Rest API"],
          live: "https://prticket.com",
            image: require('./assets/prticket.png'),
          code: false,

        },
        {
          name: "Quote SMS",
          tags: ["Spring Boot", "Java", "Twilio"],
          live: false,
          image: require('./assets/twilio.png'),
          code: "https://github.com/ken-bem/sms"
        },
        {
          name: "Portfolio",
          tags: ["Vue", "Tailwind"],
            live: "/",
            code: "https://github.com/ken-bem/portfolio",
            image: require('./assets/portfolio.png'),
        },
        {
          name: "Primavera",
          tags: ["Spring Boot", "Java", "Mysql", "Templates"],
          live: false,
          image: require('./assets/spring.png'),
          code: "https://github.com/ken-bem/primavera"
        },
        {
            name: "Puerto Rico Produce",
            tags: ["VueJS", "Netlify", "Rest API"],
            live: "https://zealous-swartz-adcf80.netlify.com/",
            code: "https://github.com/ken-bem/puertoricoproduce",
            image: require('./assets/produce.png'),
        }
      ],
      links: {
        github: "https://github.com/ken-bem/",
        linkedIn: "https://www.linkedin.com/in/kenneth-reyes-ken-bem/",
        email: "mailto:kgabrielr@yahoo.com"
      }
    }
  },
}
</script>

<style lang="scss">
    @import "./styles/main.scss";
#app {
  font-family: 'Montserrat', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}


</style>
