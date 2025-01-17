<template>
  <div class="min-h-screen">

    <!-- Events Section -->
    <main class="py-8 px-4">
      <div class="max-w-7xl mx-auto">
        <!-- Title -->
        <h2 class="text-3xl font-bold text-black text-center mb-6">
          Rekhatama Event
        </h2>

        <!-- Grid Layout for Events -->
        <div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 gap-6" >
          <div
            v-for="(event, index) in events"
            :key="index"
            class="bg-white rounded-lg shadow-lg p-4"
            data-aos="zoom-in-down"
          >
            <h3 class="text-lg font-semibold text-gray-800 mb-2">
              {{ event.name }}
            </h3>
            <p class="text-gray-600 text-sm mb-4 line-clamp-2">
              {{ event.description }}
            </p>
            <p class="text-gray-800 font-medium text-sm mb-2">
              <b>Date:</b> {{ event.date }}
            </p>
            <p class="text-gray-800 font-medium text-sm">
              <b>Location:</b> {{ event.location }}
            </p>
            <div class="mt-4">
              <button
                class="w-full bg-indigo-600 text-white py-2 rounded-md hover:bg-indigo-700 transition-colors"
                @click="registerForEvent(event.id)"
              >
                Register
              </button>
            </div>
          </div>
        </div>
      </div>
    </main>
  </div>
</template>

<script>
export default {
  data() {
    return {
      events: [
        { id: 1, name: "Tech Conference 2025", description: "Join us for the annual tech conference with keynotes and breakout sessions.", date: "March 20, 2025", location: "New York, NY" },
        { id: 2, name: "Music Festival", description: "Enjoy live performances from top artists at the biggest music festival of the year.", date: "April 5, 2025", location: "Los Angeles, CA" },
        { id: 3, name: "Startup Pitch Competition", description: "Watch the brightest startups pitch their innovative ideas to industry leaders.", date: "May 15, 2025", location: "San Francisco, CA" },
      ],
    };
  },
  methods: {
    registerForEvent(eventId) {
      alert(`You have registered for the event with ID: ${eventId}`);
    },
  },
};
</script>

<style scoped>
/* Truncate text for long descriptions */
.line-clamp-2 {
  display: -webkit-box;
  -webkit-line-clamp: 2;
  -webkit-box-orient: vertical;
  overflow: hidden;
}
</style>
