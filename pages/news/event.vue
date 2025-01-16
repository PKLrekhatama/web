<template>
    <div>
      <!-- Breadcrumbs Component -->
      <Breadcrumbs :breadcrumbs="breadcrumbList" />
    </div>
    <eventPage/>
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
          { label: "Event", url: "/news/event" },
        ],
      };
    },
  };
  </script>
  
  <style>
  /* Optional global styles */
  </style>
  