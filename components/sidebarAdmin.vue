<template>
  <div class="sticky top-0">
    <div
      class="w-[300px] p-2 flex flex-col items-center justify-center gap-2 bg-slate-50 h-screen overflow-y-auto"
    >
      <div class="mb-8 mt-4">
        <img
          src="https://www.rekhatama.com/rekha/sites/default/files/Logo%20Web%2040px.jpg"
          alt=""
        />
      </div>
      <span class="font-bold underline"></span>
      <label
        class="inline-flex justify-start w-full items-center z-10 p-2 border border-transparent has-[:checked]:border-indigo-500 has-[:checked]:text-indigo-900 has-[:checked]:bg-indigo-50 has-[:checked]:font-bold hover:bg-slate-200 transition-all cursor-pointer has-[:checked]:transition-all has-[:checked]:duration-500 duration-500 relative [&amp;_p]:has-[:checked]:translate-y-0 [&amp;_p]:has-[:checked]:transition-transform [&amp;_p]:has-[:checked]:duration-500 [&amp;_p]:has-[:checked]:opacity-100 overflow-hidden"
      >
        <div
          class="inline-flex items-center justify-center gap-2 relative mr-3"
        >
          <svg
            xmlns="http://www.w3.org/2000/svg"
            width="30"
            height="30"
            viewBox="0 0 24 24"
            fill="none"
            stroke="#000000"
            stroke-width="2"
            stroke-linecap="round"
            stroke-linejoin="round"
          >
            <path d="M20 21v-2a4 4 0 0 0-4-4H8a4 4 0 0 0-4 4v2"></path>
            <circle cx="12" cy="7" r="4"></circle>
          </svg>
          <p
            class="font-semibold absolute inset-0 w-full whitespace-nowrap translate-y-[110%] translate-x-full top-1 left-2 transition-all duration-700 opacity-0"
          >
            Google Pay
          </p>
        </div>
        <a href="/admin/">
          <input
            class="checked:text-indigo-500 checked:ring-0 checked:ring-current focus:ring-0 focus:ring-current"
            value="User"
            name="payment"
            type="submit"
          />
        </a>
      </label>
      <label
        class="inline-flex justify-start w-full items-center rounded-lg p-2 border border-transparent has-[:checked]:border-indigo-500 has-[:checked]:text-indigo-900 has-[:checked]:bg-indigo-50 has-[:checked]:font-bold hover:bg-slate-200 transition-all cursor-pointer has-[:checked]:transition-all has-[:checked]:duration-500 duration-500 relative [&amp;_p]:has-[:checked]:translate-y-0 [&amp;_p]:has-[:checked]:transition-transform [&amp;_p]:has-[:checked]:duration-500 [&amp;_p]:has-[:checked]:opacity-100 overflow-hidden"
      >
        <div class="inline-flex items-center justify-start gap-2 relative mr-2">
          <ion-icon
            name="newspaper-outline"
            style="width: 30px; height: 30px"
          ></ion-icon>
          <p
            class="font-semibold absolute inset-0 w-full whitespace-nowrap -translate-y-[110%] translate-x-full top-1 left-2 transition-all duration-700 opacity-0"
          >
            Apple Pay
          </p>
        </div>
        <a href="/admin/career/">
          <input
            class="checked:text-indigo-500 checked:ring-0 checked:ring-current focus:ring-0 focus:ring-current"
            value="Career"
            name="payment"
            type="submit"
          />
        </a>
      </label>
      <label
        class="inline-flex justify-start w-full items-center rounded-lg p-2 border border-transparent has-[:checked]:border-indigo-500 has-[:checked]:text-indigo-900 has-[:checked]:bg-indigo-50 has-[:checked]:font-bold hover:bg-slate-200 transition-all cursor-pointer has-[:checked]:transition-all has-[:checked]:duration-500 duration-500 relative [&amp;_p]:has-[:checked]:translate-y-0 [&amp;_p]:has-[:checked]:transition-transform [&amp;_p]:has-[:checked]:duration-500 [&amp;_p]:has-[:checked]:opacity-100 overflow-hidden"
      >
        <div class="inline-flex items-center justify-start gap-2 relative mr-2">
          <ion-icon
            name="cart-outline"
            style="width: 30px; height: 30px"
          ></ion-icon>
          <p
            class="font-semibold absolute inset-0 w-full whitespace-nowrap -translate-y-[110%] translate-x-full top-1 left-2 transition-all duration-700 opacity-0"
          >
            Apple Pay
          </p>
        </div>
        <a href="/admin/store/">
          <input
            class="checked:text-indigo-500 checked:ring-0 checked:ring-current focus:ring-0 focus:ring-current"
            value="Store"
            name="payment"
            type="submit"
          />
        </a>
      </label>
      <label
        class="inline-flex justify-start w-full items-center rounded-lg p-2 border border-transparent has-[:checked]:border-indigo-500 has-[:checked]:text-indigo-900 has-[:checked]:bg-indigo-50 has-[:checked]:font-bold hover:bg-slate-200 transition-all cursor-pointer has-[:checked]:transition-all has-[:checked]:duration-500 duration-500 relative [&amp;_p]:has-[:checked]:translate-y-0 [&amp;_p]:has-[:checked]:transition-transform [&amp;_p]:has-[:checked]:duration-500 [&amp;_p]:has-[:checked]:opacity-100 overflow-hidden"
      >
        <div class="inline-flex items-center justify-start gap-2 relative mr-2">
          <ion-icon
            name="book-outline"
            style="width: 30px; height: 30px"
          ></ion-icon>
          <p
            class="font-semibold absolute inset-0 w-full whitespace-nowrap -translate-y-[110%] translate-x-full top-1 left-2 transition-all duration-700 opacity-0"
          >
            Apple Pay
          </p>
        </div>
        <a href="/admin/article/">
          <input
            class="checked:text-indigo-500 checked:ring-0 checked:ring-current focus:ring-0 focus:ring-current"
            value="Articles"
            name="payment"
            type="submit"
          />
        </a>
      </label>
      <label
        class="inline-flex justify-start w-full items-center rounded-lg p-2 border border-transparent has-[:checked]:border-indigo-500 has-[:checked]:text-indigo-900 has-[:checked]:bg-indigo-50 has-[:checked]:font-bold hover:bg-slate-200 transition-all cursor-pointer has-[:checked]:transition-all has-[:checked]:duration-500 duration-500 relative [&amp;_p]:has-[:checked]:translate-y-0 [&amp;_p]:has-[:checked]:transition-transform [&amp;_p]:has-[:checked]:duration-500 [&amp;_p]:has-[:checked]:opacity-100 overflow-hidden"
      >
        <div class="inline-flex items-center justify-start gap-2 relative mr-2">
          <ion-icon
            name="receipt-outline"
            style="width: 30px; height: 30px"
          ></ion-icon>
          <p
            class="font-semibold absolute inset-0 w-full whitespace-nowrap -translate-y-[110%] translate-x-full top-1 left-2 transition-all duration-700 opacity-0"
          >
            Apple Pay
          </p>
        </div>
        <a href="/admin/category/">
          <input
            class="checked:text-indigo-500 checked:ring-0 checked:ring-current focus:ring-0 focus:ring-current"
            value="Category"
            name="payment"
            type="submit"
          />
        </a>
      </label>
      <label
        class="mb-28 inline-flex justify-start w-full items-center rounded-lg p-2 border border-transparent has-[:checked]:border-indigo-500 has-[:checked]:text-indigo-900 has-[:checked]:bg-indigo-50 has-[:checked]:font-bold hover:bg-slate-200 transition-all cursor-pointer has-[:checked]:transition-all has-[:checked]:duration-500 duration-500 relative [&amp;_p]:has-[:checked]:translate-y-0 [&amp;_p]:has-[:checked]:transition-transform [&amp;_p]:has-[:checked]:duration-500 [&amp;_p]:has-[:checked]:opacity-100 overflow-hidden"
      >
        <div class="inline-flex items-center justify-start gap-2 relative mr-2">
          <ion-icon
            name="today-outline"
            style="width: 30px; height: 30px"
          ></ion-icon>
          <p
            class="font-semibold absolute inset-0 w-full whitespace-nowrap -translate-y-[110%] translate-x-full top-1 left-2 transition-all duration-700 opacity-0"
          >
            Apple Pay
          </p>
        </div>
        <a href="/admin/event/">
          <input
            class="checked:text-indigo-500 checked:ring-0 checked:ring-current focus:ring-0 focus:ring-current"
            value="Event"
            name="payment"
            type="submit"
          />
        </a>
      </label>
      <label
        class="inline-flex justify-start w-full items-center rounded-lg p-2 border border-transparent has-[:checked]:border-indigo-500 has-[:checked]:text-indigo-900 has-[:checked]:bg-indigo-50 has-[:checked]:font-bold hover:bg-slate-200 transition-all cursor-pointer has-[:checked]:transition-all has-[:checked]:duration-500 duration-500 relative [&amp;_p]:has-[:checked]:translate-y-0 [&amp;_p]:has-[:checked]:transition-transform [&amp;_p]:has-[:checked]:duration-500 [&amp;_p]:has-[:checked]:opacity-100 overflow-hidden"
      >
        <div class="inline-flex items-center justify-start gap-2 relative mr-2">
          <ion-icon
            name="log-out-outline"
            style="width: 30px; height: 30px"
          ></ion-icon>
          <p
            class="font-semibold absolute inset-0 w-full whitespace-nowrap -translate-y-[110%] translate-x-full top-1 left-2 transition-all duration-700 opacity-0"
          >
            Apple Pay
          </p>
        </div>
        <button
          @click="handleLogout"
          class="checked:text-indigo-500 checked:ring-0 checked:ring-current focus:ring-0 focus:ring-current"
        >
          Log Out
        </button>
      </label>
    </div>
  </div>
  <!-- Logout Animation Modal -->
  <div
    v-if="isLoggingOut"
    class="fixed inset-0 bg-gray-900 backdrop-blur-lg bg-opacity-50 flex items-center justify-center z-50"
  >
    <div
      class="w-28 h-28 border-8 text-blue-400 text-4xl animate-spin border-gray-300 flex items-center justify-center border-t-blue-400 rounded-full"
    >
      <img src="http://localhost:3000/_nuxt/assets/img/Logo.png" alt="Logo" />
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      isLoggingOut: false, // Status logout
    };
  },
  methods: {
    handleLogout() {
      // Tampilkan animasi logout
      this.isLoggingOut = true;

      // Simulasikan delay sebelum logout (misalnya 3 detik)
      setTimeout(() => {
        // Arahkan ke halaman lain setelah logout
        this.$router.push("/");
      }, 3000); // Durasi animasi (3 detik)
    },
  },
};
</script>
<style scoped>
html,
body {
  margin: 0;
  height: 100%;
  overflow: hidden;
}
</style>
