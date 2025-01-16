<template>
    <nav class="bg-gray-100 py-3 px-5 rounded-lg shadow-md">
      <ul class="flex items-center space-x-2">
        <li v-for="(breadcrumb, index) in breadcrumbs" :key="index" class="flex items-center">
          <!-- Breadcrumb Link -->
          <router-link
            v-if="index !== breadcrumbs.length - 1"
            :to="breadcrumb.url"
            class="text-blue-600 hover:text-blue-800 transition"
          >
            {{ breadcrumb.label }}
          </router-link>
          <span v-else class="text-gray-500">{{ breadcrumb.label }}</span>
  
          <!-- Separator -->
          <span v-if="index !== breadcrumbs.length - 1" class="mx-2 text-gray-400">
            /
          </span>
        </li>
      </ul>
    </nav>
  </template>
  
  <script>
  export default {
    props: {
      breadcrumbs: {
        type: Array,
        required: true,
        default: () => [],
      },
    },
  };
  </script>
  
  <style scoped>
  /* Optional: Additional styling for the breadcrumbs */
  </style>
  