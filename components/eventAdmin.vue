<template>
    <div class="p-6">
      <!-- Header -->
      <h1 class="text-2xl font-bold mb-4">Event Management</h1>
  
      <!-- Tombol Tambah Event -->
      <button
        class="bg-blue-500 text-white px-4 py-2 rounded shadow hover:bg-blue-600 mb-4"
        @click="openAddEventModal"
      >
        + Tambah Event
      </button>
  
      <!-- Tabel Data Event -->
      <table class="table-auto w-full border-collapse border border-gray-300">
        <thead>
          <tr class="bg-gray-200">
            <th class="border border-gray-300 px-4 py-2">#</th>
            <th class="border border-gray-300 px-4 py-2">Nama Event</th>
            <th class="border border-gray-300 px-4 py-2">Tanggal</th>
            <th class="border border-gray-300 px-4 py-2">Keterangan</th>
            <th class="border border-gray-300 px-4 py-2">Aksi</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="(event, index) in events" :key="event.id" class="hover:bg-gray-100">
            <td class="border border-gray-300 px-4 py-2 text-center">{{ index + 1 }}</td>
            <td class="border border-gray-300 px-4 py-2">{{ event.name }}</td>
            <td class="border border-gray-300 px-4 py-2">{{ event.date }}</td>
            <td class="border border-gray-300 px-4 py-2">{{ event.description }}</td>
            <td class="border border-gray-300 px-4 py-2 text-center">
              <button
                class="bg-red-500 text-white px-3 py-1 rounded shadow hover:bg-red-600"
                @click="deleteEvent(index)"
              >
                Hapus
              </button>
            </td>
          </tr>
          <tr v-if="events.length === 0">
            <td colspan="5" class="text-center text-gray-500 py-4">Tidak ada data event.</td>
          </tr>
        </tbody>
      </table>
  
      <!-- Modal Tambah Event -->
      <div
        v-if="isAddEventModalVisible"
        class="fixed inset-0 bg-black bg-opacity-50 flex items-center justify-center z-50"
      >
        <div class="bg-white p-6 rounded-lg w-96">
          <h2 class="text-lg font-bold mb-4">Tambah Event</h2>
          <form @submit.prevent="addEvent">
            <div class="mb-4">
              <label for="eventName" class="block text-sm font-medium mb-2">Nama Event</label>
              <input
                v-model="newEvent.name"
                id="eventName"
                type="text"
                class="w-full border border-gray-300 rounded px-3 py-2"
                placeholder="Masukkan nama event"
                required
              />
            </div>
            <div class="mb-4">
              <label for="eventDate" class="block text-sm font-medium mb-2">Tanggal</label>
              <input
                v-model="newEvent.date"
                id="eventDate"
                type="date"
                class="w-full border border-gray-300 rounded px-3 py-2"
                required
              />
            </div>
            <div class="mb-4">
              <label for="eventDescription" class="block text-sm font-medium mb-2">Keterangan</label>
              <textarea
                v-model="newEvent.description"
                id="eventDescription"
                class="w-full border border-gray-300 rounded px-3 py-2"
                placeholder="Masukkan keterangan event"
                rows="3"
                required
              ></textarea>
            </div>
            <div class="flex justify-end gap-2">
              <button
                type="button"
                class="bg-gray-300 px-4 py-2 rounded hover:bg-gray-400"
                @click="closeAddEventModal"
              >
                Batal
              </button>
              <button
                type="submit"
                class="bg-blue-500 text-white px-4 py-2 rounded shadow hover:bg-blue-600"
              >
                Simpan
              </button>
            </div>
          </form>
        </div>
      </div>
    </div>
  </template>

<script>
export default {
  data() {
    return {
      events: [], // Daftar event
      isAddEventModalVisible: false, // Status modal tambah event
      newEvent: {
        name: "",
        date: "",
        description: "",
      }, // Data untuk event baru
    };
  },
  methods: {
    // Buka modal tambah event
    openAddEventModal() {
      this.isAddEventModalVisible = true;
    },

    // Tutup modal tambah event
    closeAddEventModal() {
      this.isAddEventModalVisible = false;
      this.resetNewEvent();
    },

    // Tambah event ke daftar
    addEvent() {
      if (this.newEvent.name && this.newEvent.date && this.newEvent.description) {
        this.events.push({ ...this.newEvent, id: Date.now() });
        this.closeAddEventModal();
      }
    },

    // Hapus event dari daftar
    deleteEvent(index) {
      this.events.splice(index, 1);
    },

    // Reset data event baru
    resetNewEvent() {
      this.newEvent = {
        name: "",
        date: "",
        description: "",
      };
    },
  },
};
</script>
