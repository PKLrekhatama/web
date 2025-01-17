<template>
  <!-- Store Content -->
  <main class="py-8 px-4">
      <div class="max-w-7xl mx-auto">
        <!-- Title -->
        <h2 class="text-3xl font-bold text-black text-center mb-6">
          Our Product
        </h2>

        <!-- Grid Layout for Products -->
        <div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-4 gap-6" >
          <div
            v-for="(product, index) in products"
            :key="index"
            class="bg-white rounded-lg shadow-lg p-3"
            data-aos="fade-up"
            data-aos-anchor-placement="top-center"
          >
            <h3 class="text-lg font-semibold text-gray-800 mb-2">
              {{ product.name }}
            </h3>
            <p class="text-gray-600 text-sm mb-4 line-clamp-2">
              {{ product.description }}
            </p>
            <p class="text-indigo-600 font-bold text-lg">
              {{ product.price }}
            </p>
            <div class="p-3 border-t"> <!-- Reduced padding -->
              <button
                class="w-full bg-indigo-600 text-white py-2 rounded-md hover:bg-indigo-700 transition-colors"
                @click="addToCart(product.id)"
              >
                Add to Cart
              </button>
            </div>
          </div>
        </div>
      </div>
    </main>
</template>
<script>
export default {
  data() {
    return {
      products: [
        // List of products without images
        { id: 1, name: "Wireless Headphones", description: "High-quality wireless headphones with noise cancellation.", price: 99.99 },
        { id: 2, name: "Smart Watch", description: "Track your fitness and stay connected with this smartwatch.", price: 149.99 },
        { id: 3, name: "Bluetooth Speaker", description: "Portable Bluetooth speaker with crystal-clear sound.", price: 49.99 },
        { id: 4, name: "Apaja Speaker", description: "Portable Bluetooth speaker with crystal-clear sound.", price: 49.99 }, // Memperbaiki ID yang sama
      ],
    };
  },
  methods: {
    addToCart(productId) {
      alert(`Product with ID: ${productId} added to cart!`);
    },
  },
};
</script>

<style scoped>
/* Truncate text for long descriptions */
.line-clamp-2 {
  display: -webkit-box;
  -webkit-line-clamp: 2;
  -webkit-box-orient: vertical;
  overflow: hidden;
}
</style>