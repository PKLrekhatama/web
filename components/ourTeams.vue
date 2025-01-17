<template>
  <div class="con min-h-screen pt-5">
    <div class="bg-white rounded-r-lg p-4 w-52 tag">
      <div class="w-full flex items-center justify-center">
        <h1 class="font-bold">Our Teams</h1>
      </div>
    </div>
    <div class="flex flex-wrap justify-center gap-6 p-6">
      <!-- Card Template -->
      <div
        class="group relative w-80 h-72 bg-slate-50 flex flex-col items-center justify-center gap-2 text-center rounded-2xl overflow-hidden transition-all duration-500 shadow-lg shadow-gray-900/100"
      >
        <!-- Smooth Background Hover Effect -->
        <div
          class="absolute top-0 left-0 w-full h-24 bg-gradient-to-bl from-indigo-500 via-purple-500 to-pink-500 rounded-t-2xl transform transition-all duration-700 ease-in-out group-hover:h-44 group-hover:scale-95"
        ></div>
        <!-- Profile Picture -->
        <div
          class="relative z-10 w-28 h-28 rounded-full border-4 border-slate-50 transition-transform duration-500 ease-in-out group-hover:scale-150 group-hover:-translate-x-24 group-hover:-translate-y-20"
        >
          <img
            src="https://www.rekhatama.com/rekha/themes/tarapro/images/demo/team/endra.jpeg"
            alt=""
            class="rounded-full"
          />
        </div>
        <!-- Profile Info -->
        <div
          class="relative z-10 transition-transform duration-500 ease-in-out group-hover:-translate-y-10"
        >
          <span class="text-2xl font-semibold">George Johnson</span>
          <p>Support Specialist</p>
        </div>
        <!-- Follow Button -->
        <a
          class="relative z-10 bg-blue-700 px-4 py-1 text-slate-50 rounded-md hover:scale-125 transition-transform duration-500 ease-in-out hover:bg-blue-500"
          href="#"
          >Follow</a
        >
      </div>
      <!-- Dupe Card Template -->
      <div
        class="group relative w-80 h-72 bg-slate-50 flex flex-col items-center justify-center gap-2 text-center rounded-2xl overflow-hidden transition-all duration-500 shadow-lg shadow-gray-900/100"
      >
        <!-- Smooth Background Hover Effect -->
        <div
          class="absolute top-0 left-0 w-full h-24 bg-gradient-to-bl from-indigo-500 via-purple-500 to-pink-500 rounded-t-2xl transform transition-all duration-700 ease-in-out group-hover:h-44 group-hover:scale-95 "
        ></div>
        <!-- Profile Picture -->
        <div
          class="relative z-10 w-28 h-28 rounded-full border-4 border-slate-50 transition-transform duration-500 ease-in-out group-hover:scale-150 group-hover:-translate-x-24 group-hover:-translate-y-20"
        >
          <img
            src="https://www.rekhatama.com/rekha/themes/tarapro/images/demo/team/triana.jpg"
            alt=""
            class="rounded-full"
          />
        </div>
        <!-- Profile Info -->
        <div
          class="relative z-10 transition-transform duration-500 ease-in-out group-hover:-translate-y-10"
        >
          <span class="text-2xl font-semibold">George Johnson</span>
          <p>Support Specialist</p>
        </div>
        <!-- Follow Button -->
        <a
          class="relative z-10 bg-blue-700 px-4 py-1 text-slate-50 rounded-md hover:scale-125 transition-transform duration-500 ease-in-out hover:bg-blue-500"
          href="#"
          >Follow</a
        >
      </div>
      <!-- Dupe Card Template -->
      <div
        class="group relative w-80 h-72 bg-slate-50 flex flex-col items-center justify-center gap-2 text-center rounded-2xl overflow-hidden transition-all duration-500 shadow-lg shadow-gray-900/100"
      >
        <!-- Smooth Background Hover Effect -->
        <div
          class="absolute top-0 left-0 w-full h-24 bg-gradient-to-bl from-indigo-500 via-purple-500 to-pink-500 rounded-t-2xl transform transition-all duration-700 ease-in-out group-hover:h-44 group-hover:scale-95"
        ></div>
        <!-- Profile Picture -->
        <div
          class="relative z-10 w-28 h-28 rounded-full border-4 border-slate-50 transition-transform duration-500 ease-in-out group-hover:scale-150 group-hover:-translate-x-24 group-hover:-translate-y-20"
        >
          <img
            src="https://www.rekhatama.com/rekha/themes/tarapro/images/demo/team/syafira.jpg"
            alt=""
            class="rounded-full"
          />
        </div>
        <!-- Profile Info -->
        <div
          class="relative z-5 transition-transform duration-500 ease-in-out group-hover:-translate-y-10"
        >
          <span class="text-2xl font-semibold">George Johnson</span>
          <p>Support Specialist</p>
        </div>
        <!-- Follow Button -->
        <a
          class="relative z-10 bg-blue-700 px-4 py-1 text-slate-50 rounded-md hover:scale-125 transition-transform duration-500 ease-in-out hover:bg-blue-500"
          href="#"
          >Follow</a
        >
      </div>
    </div>
  </div>
</template>

<style scoped>
.tag {
  box-shadow: 5px 4px 16px 0px rgba(0, 0, 0, 0.75);
  -webkit-box-shadow: 5px 4px 16px 0px rgba(0, 0, 0, 0.75);
  -moz-box-shadow: 5px 4px 16px 0px rgba(0, 0, 0, 0.75);
}
</style>
