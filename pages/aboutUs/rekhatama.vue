<template>
    <div>
      <!-- Breadcrumbs Component -->
      <Breadcrumbs :breadcrumbs="breadcrumbList" />
    </div>
    <aboutRekhatama/>
  </template>
  
  <script>
  import Breadcrumbs from "./components/Breadcrumbs.vue";
  
  export default {
    components: {
      Breadcrumbs,
    },
    data() {
      return {
        breadcrumbList: [
          { label: "Home", url: "/" },
          { label: "Rekhatama", url: "/aboutUs/rekhatama" },
        ],
      };
    },
  };
  </script>
  
  <style>
  /* Optional global styles */
  </style>
  