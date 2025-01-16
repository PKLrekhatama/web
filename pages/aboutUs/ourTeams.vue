<template>
    <div>
      <!-- Breadcrumbs Component -->
      <Breadcrumbs :breadcrumbs="breadcrumbList" />
    </div>
    <ourTeams/>
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
          { label: "Our Teams", url: "/aboutUs/ourTeams" },
        ],
      };
    },
  };
  </script>
  
  <style>
  /* Optional global styles */
  </style>
  