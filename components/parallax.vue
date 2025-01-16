<template>
    <div class="parallax flex flex-col justify-center items-center min-h-screen bg-cover bg-center">
      <div class="bg-white bg-opacity-75 rounded-lg shadow-lg p-4 md:p-6 text-center max-w-xs sm:max-w-sm md:max-w-md">
        <h1 class="text-black text-2xl sm:text-3xl font-bold mb-2 sm:mb-4">
          Welcome to Rekhatama
        </h1>
        <p class="text-black text-sm sm:text-base font-medium">
          Discover amazing things here!
        </p>
      </div>
    </div>
  </template>
  
  <style scoped>
  .parallax {
    /* The image used */
    background-image: url("/assets/img/bg.jpg");
  
    /* Set a specific height */
    min-height: 500px;
  
    /* Create the parallax scrolling effect */
    background-attachment: fixed;
    background-position: center;
    background-repeat: no-repeat;
    background-size: cover;
  }
  
  /* Fallback for mobile devices that do not support `background-attachment: fixed` */
  @media (max-width: 768px) {
    .parallax {
      background-attachment: scroll;
    }
  }
  </style>
  