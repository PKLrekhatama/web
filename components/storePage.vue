<template>
    <div class="con min-h-screen py-4 px-2">
      <!-- Store Content -->
      <main class="py-4 px-2">
        <div class="max-w-7xl mx-auto">
          <!-- Title -->
          <h2 class="text-3xl font-bold text-black text-center mb-4">
            Our Product
          </h2>
  
          <!-- Grid Layout for Products -->
          <div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-4 gap-4">
            <div
              v-for="(product, index) in products"
              :key="index"
              class="bg-white rounded-lg shadow-lg p-3 hover:scale-105 transition-transform duration-150"
            >
              <h3 class="text-base font-semibold text-gray-800 mb-2">
                {{ product.name }}
              </h3>
              <p class="text-gray-600 text-sm mb-3 line-clamp-2">
                {{ product.description }}
              </p>
              <p class="text-indigo-600 font-bold text-md">
                ${{ product.price }}
              </p>
              <div class="mt-4">
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
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        products: [
          { id: 1, name: "Wireless Headphones", description: "High-quality wireless headphones with noise cancellation.", price: 99.99 },
          { id: 2, name: "Smart Watch", description: "Track your fitness and stay connected with this smartwatch.", price: 149.99 },
          { id: 3, name: "Bluetooth Speaker", description: "Portable Bluetooth speaker with crystal-clear sound.", price: 49.99 },
          { id: 4, name: "4K Action Camera", description: "Capture stunning 4K videos with this waterproof action camera.", price: 199.99 },
          { id: 5, name: "Gaming Mouse", description: "Ergonomic gaming mouse with customizable RGB lighting.", price: 29.99 },
          { id: 6, name: "Laptop Stand", description: "Adjustable laptop stand for better posture and comfort.", price: 39.99 },
          { id: 7, name: "Portable Charger", description: "Charge your devices on the go with this compact portable charger.", price: 19.99 },
          { id: 8, name: "Smartphone Gimbal", description: "Stabilize your smartphone videos with this advanced gimbal.", price: 89.99 },
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
  