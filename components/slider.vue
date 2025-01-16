<template>
    <div class="relative w-full max-w-4xl mx-auto overflow-hidden rounded-lg shadow-lg mt-5 mb-5" data-aos="fade-left">
      <!-- Slides -->
      <div
        class="flex transition-transform duration-500"
        :style="{ transform: `translateX(-${currentIndex * 100}%)` }"
      >
        <div
          v-for="(slide, index) in slides"
          :key="index"
          class="w-full flex-shrink-0"
        >
          <img
            :src="slide.image"
            :alt="'Slide ' + (index + 1)"
            class="w-full h-56 sm:h-72 md:h-96 lg:h-[28rem] object-cover"
          />
        </div>
      </div>
  
      <!-- Navigation Buttons -->
      <button
        class="absolute top-1/2 left-4 transform -translate-y-1/2 bg-gray-800 bg-opacity-50 text-white p-3 md:p-4 rounded-full hover:bg-opacity-75 focus:outline-none"
        @click="prevSlide"
      >
        &#10094;
      </button>
      <button
        class="absolute top-1/2 right-4 transform -translate-y-1/2 bg-gray-800 bg-opacity-50 text-white p-3 md:p-4 rounded-full hover:bg-opacity-75 focus:outline-none"
        @click="nextSlide"
      >
        &#10095;
      </button>
  
      <!-- Dots -->
      <div class="absolute bottom-4 left-1/2 transform -translate-x-1/2 flex space-x-3">
        <span
          v-for="(slide, index) in slides"
          :key="index"
          class="w-3 h-3 md:w-4 md:h-4 rounded-full bg-white bg-opacity-50 hover:bg-opacity-100 cursor-pointer"
          :class="{ 'bg-opacity-100': index === currentIndex }"
          @click="goToSlide(index)"
        ></span>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        slides: [
          {
            image:
              "https://images.unsplash.com/photo-1455849318743-b2233052fcff?q=80&w=2069&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D",
          },
          {
            image:
              "https://images.unsplash.com/photo-1476937673710-8174834aa065?q=80&w=2070&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D",
          },
          {
            image:
              "https://images.unsplash.com/photo-1571387816689-fa4855e874e4?q=80&w=2070&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D",
          },
        ],
        currentIndex: 0,
        interval: null,
      };
    },
    methods: {
      nextSlide() {
        this.currentIndex = (this.currentIndex + 1) % this.slides.length;
      },
      prevSlide() {
        this.currentIndex =
          (this.currentIndex - 1 + this.slides.length) % this.slides.length;
      },
      goToSlide(index) {
        this.currentIndex = index;
      },
      startAutoSlide() {
        this.interval = setInterval(() => {
          this.nextSlide();
        }, 5000);
      },
      stopAutoSlide() {
        clearInterval(this.interval);
      },
    },
    mounted() {
      this.startAutoSlide();
    },
    beforeDestroy() {
      this.stopAutoSlide();
    },
  };
  </script>
  
  <style scoped>
  /* Tambahan opsional jika ingin menyesuaikan lebih lanjut */
  </style>
  