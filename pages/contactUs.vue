<template>
    <div>
      <!-- Breadcrumbs Component -->
      <Breadcrumbs :breadcrumbs="breadcrumbList" />
    </div>
    <contactUs/>
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
          { label: "Contact Us", url: "/aboutUs/contactUs" },
        ],
      };
    },
  };
  </script>
  
  <style>
  /* Optional global styles */
  </style>
  