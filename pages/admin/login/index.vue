<template>
  <div class="flex items-center justify-center align-center">
    <div
      class="shadow-lg shadow-blue-500/100 bg-gray-900 border-[2px] border-blue-900 rounded-2xl hover:border-blue-500 transition-all duration-200"
    >
      <div
        class="mx-auto flex items-center space-y-4 py-16 px-12 font-semibold text-gray-500 flex-col"
      >
        <img src="/assets/img/Logo.png" alt="" class="size-20" />
        <h1 class="text-white text-2xl">Rekhindo Pratama</h1>
        <input
          class="w-full p-2 bg-blue-900 rounded-md border border-gray-700 focus:border-blue-700 hover:border-blue-500 transition-all duration-200"
          placeholder="Email"
          type="email"
          name="email"
          id=""
        />
        <input
          class="w-full p-2 bg-blue-900 rounded-md border border-gray-700 focus:border-blue-700 hover:border-blue-500 transition-all duration-200"
          placeholder="Password"
          type="password"
          name="password"
          id=""
        />
        <a href="/admin/">
          <button>
            <span class="button_top"> Sign In </span>
          </button>
        </a>
      </div>
    </div>
  </div>
</template>

<script>
definePageMeta({
  layout: "login",
});
</script>

<style scoped>
/* From Uiverse.io by Voxybuns */
button {
  /* Variables */
  --button_radius: 0.75em;
  --button_color: #e8e8e8;
  --button_outline_color: #007bff;
  font-size: 17px;
  font-weight: bold;
  border: none;
  cursor: pointer;
  border-radius: var(--button_radius);
  background: var(--button_outline_color);
}

.button_top {
  display: block;
  box-sizing: border-box;
  border: 2px solid var(--button_outline_color);
  border-radius: var(--button_radius);
  padding: 0.75em 1.5em;
  background: var(--button_color);
  color: var(--button_outline_color);
  transform: translateY(-0.2em);
  transition: transform 0.1s ease;
}

button:hover .button_top {
  /* Pull the button upwards when hovered */
  transform: translateY(-0.33em);
}

button:active .button_top {
  /* Push the button downwards when pressed */
  transform: translateY(0);
}
</style>
