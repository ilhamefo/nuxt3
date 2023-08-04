<script setup>
const showMenu = ref(false);

const cardsData = ref([
  {
    thumbnail: "laravel.svg",
    title: "Laravel Framework",
    description:
      "Laravel is a popular open-source PHP web application framework with expressive syntax, providing robust features for web development.",
    button: "See My Work",
  },
  {
    thumbnail: "Golang.svg",
    title: "Go Programming Language",
    description:
      "Go (Golang) is an efficient and statically-typed programming language developed by Google, designed for concurrent systems, simplicity, and high performance web services.",
    button: "See My Work",
  },
  {
    thumbnail: "postgresql.svg",
    title: "PostgreSQL",
    description:
      "PostgreSQL is a powerful open-source relational database management system known for its extensibility, ACID compliance, and support for advanced features, ideal for complex data management and applications.",
    button: "See My Work",
  },
  {
    thumbnail: "mongo.svg",
    title: "MongoDB",
    description:
      "MongoDB is a NoSQL document-oriented database, offering high scalability, flexibility, and ease of use. It stores data in JSON-like documents and suits modern, dynamic applications and big data solutions.",
    button: "See My Work",
  },
  {
    thumbnail: "tailwindcss-ar21.svg",
    title: "Tailwind CSS",
    description:
      "Tailwind CSS is a utility-first CSS framework that provides a set of pre-defined classes to design UI components quickly, promoting rapid and customizable web development.",
    button: "See My Work",
  },
  {
    thumbnail: "Nuxt.svg",
    title: "Nuxt.js",
    description:
      "Nuxt.js is a progressive Vue.js framework that simplifies the creation of server-rendered Vue applications, enabling easy development of SEO-friendly, performant, and scalable web projects.",
    button: "See My Work",
  },
]);
</script>

<template>
  <div class="bg-[#F9F5F2] flex items-center justify-center text-slate-900">
    <div
      class="font-fira min-h-screen flex flex-col items-start justify-start w-full sm:container gap-10 px-5 sm:px-0"
    >
      <!-- Navbar -->
      <nav
        class="flex items-center justify-between w-full py-3 sm:mt-10 mt-7 relative"
      >
        <div class="flex items-center justify-start gap-2">
          <div class="text-2xl font-bold">Efo.digital</div>
        </div>
        <button class="sm:hidden flex" @click="showMenu = !showMenu">
          <IconsMenu />
        </button>

        <div
          class="hidden sm:flex flex-col sm:flex-row items-center justify-center sm:justify-end absolute sm:static top-16 right-0 bg-[#F9F5F2] w-full sm:w-fit gap-8 py-2"
        >
          <a href="#" class="font-semibold text-lg hover:text-xl">About</a>
          <a href="#" class="font-semibold text-lg hover:text-xl">What I Do</a>
          <a href="#" class="font-semibold text-lg hover:text-xl">My Work</a>
        </div>

        <div
          class=" flex-col sm:flex-row items-center justify-center sm:justify-end absolute sm:static top-16 right-0 bg-[#F9F5F2] w-full sm:w-fit gap-8 py-2"
          :class="[showMenu ? 'flex sm:hidden' : 'hidden']"
        >
          <a href="#" class="font-semibold text-lg hover:text-xl">About</a>
          <a href="#" class="font-semibold text-lg hover:text-xl">What I Do</a>
          <a href="#" class="font-semibold text-lg hover:text-xl">My Work</a>
        </div>
      </nav>

      <!-- Hero -->
      <div
        class="w-full py-10 flex flex-col sm:flex-row items-center justify-between gap-16 sm:gap-0"
      >
        <div class="flex flex-col w-full sm:w-1/2 sm:pr-10 pr-0 gap-7 sm:gap-5">
          <div class="text-[#42403F] text-xl font-normal">
            Hi, My name is Efo.
          </div>
          <div class="text-5xl font-bold">Im a Web Developer.</div>
          <div class="text-[#42403F] text-xl font-normal">
            skilled web developer, proficient in various programming languages
            and frameworks. My expertise in front-end and back-end development
            empowers my to create innovative and user-friendly web solutions.
          </div>
          <button
            class="bg-[#F7CB46] py-5 px-16 rounded-full w-full sm:w-fit ring-2 ring-black font-black text-2xl shadow-[5px_5px_0px_0px_rgb(39,39,37)] active:shadow-[2px_2px_0px_0px_rgb(39,39,37)] active:translate-y-1 hover:-translate-y-1 hover:shadow-[8px_8px_0px_0px_rgb(39,39,37)] transition-all"
          >
            Download My CV!
          </button>
        </div>
        <div class="flex w-full sm:w-1/2 items-end justify-end">
          <nuxt-img format="webp" src="images/profile.webp" alt="" class="w-[500px]" />
        </div>
      </div>

      <!-- Card -->
      <div
        class="w-full py-10 flex flex-col items-center justify-between gap-10"
      >
        <div class="flex flex-col gap-5 justify-center items-center w-full">
          <div class="text-xl text-slate-700 font-semibold">
            Passion led us here
          </div>
          <div class="text-5xl font-bold text-slate-900">What I do</div>
        </div>

        <div
          class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-10 w-full"
        >
          <Card v-for="item in cardsData">
            <template #icon>
              <nuxt-img format="webp" :src="`/images/${item.thumbnail}`" class="h-20" />
            </template>

            <template #title> {{ item.title }} </template>

            <template #subtitle>
              {{ item.description }}
            </template>

            <template #button> {{ item.button }} </template>
          </Card>
        </div>
      </div>

      <footer class="w-full flex items-center justify-center py-5">
        Built With ❤ By Efo.
      </footer>
    </div>
  </div>
</template>
