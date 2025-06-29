<script lang="ts" setup>
import { reactive } from "vue";
import Particles from "../components/Particles.vue";

const routers = reactive([
  { to: "/technology", title: "Technology" },
  { to: "/about", title: "About Me" },
  { to: "/contact", title: "Contact Me" }
]);

const articles = reactive([
  { link: "https://wsd.gitbook.io/vue3", title: "vue3" },
  { link: "https://wsd.gitbook.io/python", title: "python" },
]);

function openLink(link: string) {
  window.open(link, "_blank");
}
</script>

<template>
  <Particles />
  <section class="text-gray-400 bg-gray-950 body-font lg:px-20" style="min-height: calc(100vh - 60px);">
    <div class="container mx-auto flex px-5 pt-24 pb-10 md:flex-row flex-col items-center relative z-10">
      <div
        class="title_ lg:flex-grow md:w-1/2 lg:pr-24 md:pr-16 flex flex-col md:items-start md:text-left mb-16 md:mb-0 items-center text-center">
        <h1 class="title-font sm:text-4xl text-3xl mb-4 font-medium text-white capitalize">
          Welcome to my blog!
        </h1>
        <p class="mb-8 leading-relaxed">
          This is a spaceship exploring the frontiers of technology and sharing
          innovative thinking. Here, I will deeply explore the latest
          developments in the technology industry and show you the endless charm
          of technology, including but not limited to cutting-edge technologies
          such as artificial intelligence, blockchain, and cloud computing.
          Together, we will cross every boundary of the digital world and
          explore how technology shapes our future.
        </p>
        <div class="flex justify-start flex-wrap gap-6">
          <button
            class="inline-flex text-white bg-purple-500 border-0 py-2 px-6 focus:outline-none hover:bg-purple-600 rounded text-lg">
            <router-link to="/case">Web3 Case</router-link>
          </button>
          <button v-for="router in routers" :key="router.to"
            class="inline-flex text-gray-400 bg-gray-800 border-0 py-2 px-6 focus:outline-none hover:bg-gray-700 hover:text-white rounded text-lg">
            <router-link :to="router.to">{{ router.title }}</router-link>
          </button>
        </div>
        <h1 class="title-font sm:text-4xl text-3xl mt-8 mb-4 font-medium text-white capitalize">
          Technical Documentation
        </h1>
        <p class="mb-8 leading-relaxed">
          Below are some of my technical articles, about front-end, back-end,
          chain end, various languages, everything is included.
        </p>
        <div class="flex justify-center gap-4">
          <button v-for="article in articles" :key="article.link" @click="openLink(article.link)"
            class="inline-flex text-gray-400 bg-gray-800 border-0 py-2 px-6 focus:outline-none hover:bg-gray-700 hover:text-white rounded text-lg">
            {{ article.title }}
          </button>
        </div>
      </div>
      <div class="lg:max-w-lg lg:w-full md:w-1/2 w-5/6 grid place-items-center">
        <img class="circle_ object-cover object-center rounded " alt="hero" src="../assets/planet.png" />
      </div>
    </div>
  </section>
</template>

<style lang="less" scoped>
.circle_ {
  animation: rotate 120s linear infinite;
}

@keyframes rotate {
  0% {
    transform: rotate(0deg);
  }

  100% {
    transform: rotate(360deg);
  }
}
</style>
