<template>
    <div class=" con min-h-screen py-8 px-4">
        <div class="max-w-5xl mx-auto">
        <!-- Title -->
        <h1 class="text-3xl font-bold text-white text-center mb-6">
            Latest News & Article
        </h1>
        
        <!-- Articles Grid -->
        <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-6" data-aos="zoom-out-up">
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
                class="text-indigo-600 font-semibold hover:text-indigo-800 transition-colors"
                @click="readMore(article.id)"
                >
                Read More →
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
          image: "https://images.unsplash.com/photo-1600298882525-1ac025c98b68?q=80&w=2070&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D",
          content:
            "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Vivamus lacinia odio vitae vestibulum vestibulum. Cras venenatis euismod malesuada...",
        },
        {
          id: 2,
          title: "The Beauty of the Ocean",
          image: "https://images.unsplash.com/photo-1516692274351-aeb3c1eaefb8?q=80&w=1931&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D",
          content:
            "Phasellus tincidunt nulla ac nisi tempor, a facilisis metus pulvinar. Morbi euismod non sapien eget lacinia. Duis bibendum, lacus non cursus...",
        },
        {
          id: 3,
          title: "A Walk Through the Forest",
          image: "https://images.unsplash.com/photo-1476231682828-37e571bc172f?q=80&w=1974&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D",
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
.line-clamp-3 {
  display: -webkit-box;
  -webkit-line-clamp: 3;
  -webkit-box-orient: vertical;
  overflow: hidden;
}
.con{
    background-color: rgb(64,102,140) !important;
}
</style>