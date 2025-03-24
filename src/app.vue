<script>
export default {
  data() {
    return {
      darkMode: false,
      movies: [
      { title: "Spiderman 1", image: "/img/spid1movie.jpg" },
        { title: "Spiderman 2", image: "/img/spid2movie.jpg" },
        { title: "Spiderman 3", image: "/img/spid3movie.jpg" },
      ],
    };
  },
  methods: {
    toggleDarkMode() {
      this.darkMode = !this.darkMode;
    },
  },
};
</script>

<template>
  <div
    :class="darkMode ? 'dark bg-gray-900 text-gray-200' : 'bg-gradient-to-br from-emerald-950 to-indigo-950 text-teal-100'"
    class="min-h-screen flex flex-col items-center justify-center p-6 transition-colors"
  >
    <button
      @click="toggleDarkMode"
      class="absolute top-4 right-4 bg-gray-200 dark:bg-gray-700 text-gray-800 dark:text-gray-100 px-4 py-2 rounded-lg shadow-md"
    >
      {{ darkMode ? "Svijetla Tema" : "Tamna Tema" }}
    </button>

    <h1 class="text-[60px] font-bold text-center">
      Pozdrav, ja sam <span class="text-cyan-400">Antonio Turković</span>
    </h1>

    <div class="w-[1024px] max-w-full border-t-2 border-opacity-75 border-teal-100 my-6"></div>
    <h2 class="text-[24px] text-teal-100/75 mb-6">Moji omiljeni filmovi:</h2>
    <div class="flex flex-wrap justify-center gap-6">
      <div v-for="movie in movies" :key="movie.title" class="w-[320px]">
        <img
          :src="movie.image"
          :alt="movie.title"
          class="w-[320px] h-[480px] object-cover rounded-lg border border-gray-300 dark:border-gray-700 shadow-lg"
        />
        <p class="text-[24px] text-center mt-2">{{ movie.title }}</p>
      </div>
    </div>
  </div>
</template>


