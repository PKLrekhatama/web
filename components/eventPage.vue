<template>
  <div class="con min-h-screen pt-5">
    <div class="bg-white rounded-r-lg p-4 w-52 tag">
      <div class="w-full flex items-center justify-center">
        <h1 class="font-bold">Rekhatama Event</h1>
      </div>
    </div>
    <div class="p-6">
      <!-- Card 1 -->
      <!-- Grid Layout for Events -->
      <div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 gap-6">
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
  </div>
</template>

<script>
export default {
  data() {
    return {
      events: [
        {
          id: 1,
          name: "Tech Conference 2025",
          description:
            "Join us for the annual tech conference with keynotes and breakout sessions.",
          date: "March 20, 2025",
          location: "New York, NY",
        },
        {
          id: 2,
          name: "Music Festival",
          description:
            "Enjoy live performances from top artists at the biggest music festival of the year.",
          date: "April 5, 2025",
          location: "Los Angeles, CA",
        },
        {
          id: 3,
          name: "Startup Pitch Competition",
          description:
            "Watch the brightest startups pitch their innovative ideas to industry leaders.",
          date: "May 15, 2025",
          location: "San Francisco, CA",
        },
        {
          id: 4,
          name: "Startup Pitch Competition",
          description:
            "Watch the brightest startups pitch their innovative ideas to industry leaders.",
          date: "May 15, 2025",
          location: "San Francisco, CA",
        },
        {
          id: 4,
          name: "Startup Pitch Competition",
          description:
            "Watch the brightest startups pitch their innovative ideas to industry leaders.",
          date: "May 15, 2025",
          location: "San Francisco, CA",
        },
        {
          id: 4,
          name: "Startup Pitch Competition",
          description:
            "Watch the brightest startups pitch their innovative ideas to industry leaders.",
          date: "May 15, 2025",
          location: "San Francisco, CA",
        },
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
.tag {
  box-shadow: 5px 4px 16px 0px rgba(0, 0, 0, 0.75);
  -webkit-box-shadow: 5px 4px 16px 0px rgba(0, 0, 0, 0.75);
  -moz-box-shadow: 5px 4px 16px 0px rgba(0, 0, 0, 0.75);
}
</style>
