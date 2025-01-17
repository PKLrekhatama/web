<template>
  <div class="con min-h-screen pt-5">
    <div class="bg-white rounded-r-lg p-4 w-52 tag">
      <div class="w-full flex items-center justify-center">
        <h1 class="font-bold">Article</h1>
      </div>
    </div>
    <div class="p-6">
      <!-- Articles Grid -->
      <div
        class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-6"
        data-aos="zoom-in-up"
      >
        <div
          v-for="(article, index) in articles"
          :key="index"
          class="bg-white rounded-lg shadow-lg overflow-hidden hover:shadow-xl transition-shadow duration-300"
        >
          <!-- Image -->
          <img
            :src="article.image"
            :alt="article.title"
            class="w-full h-48 object-cover"
          />

          <!-- Content -->
          <div class="p-4">
            <h2 class="text-xl font-semibold text-gray-800 mb-2">
              {{ article.title }}
            </h2>
            <p class="text-gray-600 text-sm line-clamp-3">
              {{ article.content }}
            </p>
          </div>

          <!-- Read More -->
          <div class="p-4 border-t">
            <button
              type="submit"
              class="flex justify-center gap-2 text-lime-500 items-center mx-auto shadow-xl text-lg bg-gray-50 backdrop-blur-md lg:font-semibold isolation-auto border-gray-50 before:absolute before:w-full before:transition-all before:duration-700 before:hover:w-full before:-left-full before:hover:left-0 before:rounded-full before:bg-lime-500 hover:text-gray-50 before:-z-10 before:aspect-square before:hover:scale-150 before:hover:duration-700 relative z-10 px-4 py-2 overflow-hidden border-2 rounded-full group"
              @click="readMore(article.id)"
            >
              Explore
              <svg
                class="w-8 h-8 justify-end group-hover:rotate-90 group-hover:bg-gray-50 text-gray-50 ease-linear duration-300 rounded-full border border-gray-700 group-hover:border-none p-2 rotate-45"
                viewBox="0 0 16 19"
                xmlns="http://www.w3.org/2000/svg"
              >
                <path
                  d="M7 18C7 18.5523 7.44772 19 8 19C8.55228 19 9 18.5523 9 18H7ZM8.70711 0.292893C8.31658 -0.0976311 7.68342 -0.0976311 7.29289 0.292893L0.928932 6.65685C0.538408 7.04738 0.538408 7.68054 0.928932 8.07107C1.31946 8.46159 1.95262 8.46159 2.34315 8.07107L8 2.41421L13.6569 8.07107C14.0474 8.46159 14.6805 8.46159 15.0711 8.07107C15.4616 7.68054 15.4616 7.04738 15.0711 6.65685L8.70711 0.292893ZM9 18L9 1H7L7 18H9Z"
                  class="fill-gray-800 group-hover:fill-blue-800"
                ></path>
              </svg>
            </button>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      articles: [
        {
          id: 1,
          title: "Exploring the Mountains",
          image:
            "https://images.unsplash.com/photo-1600298882525-1ac025c98b68?q=80&w=2070&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D",
          content:
            "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Vivamus lacinia odio vitae vestibulum vestibulum. Cras venenatis euismod malesuada...",
        },
        {
          id: 2,
          title: "The Beauty of the Ocean",
          image:
            "https://images.unsplash.com/photo-1516692274351-aeb3c1eaefb8?q=80&w=1931&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D",
          content:
            "Phasellus tincidunt nulla ac nisi tempor, a facilisis metus pulvinar. Morbi euismod non sapien eget lacinia. Duis bibendum, lacus non cursus...",
        },
        {
          id: 3,
          title: "A Walk Through the Forest",
          image:
            "https://images.unsplash.com/photo-1476231682828-37e571bc172f?q=80&w=1974&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D",
          content:
            "Maecenas scelerisque risus eget blandit molestie. Aenean in consequat arcu. Nulla facilisi. Fusce id nulla id ex eleifend sodales a at erat...",
        },
      ],
    };
  },
  methods: {
    readMore(articleId) {
      alert(`Read more about article ID: ${articleId}`);
    },
  },
};
</script>

<style scoped>
.tag {
  box-shadow: 5px 4px 16px 0px rgba(0, 0, 0, 0.75);
  -webkit-box-shadow: 5px 4px 16px 0px rgba(0, 0, 0, 0.75);
  -moz-box-shadow: 5px 4px 16px 0px rgba(0, 0, 0, 0.75);
}

.before:bg-blue-500 {
  background-color: rgb(113, 171, 72);
}
</style>
