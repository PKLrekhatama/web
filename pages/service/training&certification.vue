<template>
    <div>
      <!-- Breadcrumbs Component -->
      <Breadcrumbs :breadcrumbs="breadcrumbList" />
    </div>
    <training/>
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
          { label: "Training & Certification", url: "/service/training%26certification" },
        ],
      };
    },
  };
  </script>
  
  <style>
  /* Optional global styles */
  </style>
  