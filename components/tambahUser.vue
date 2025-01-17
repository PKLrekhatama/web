<template>
  <div class="container mx-auto p-6 bg-gray-100 h-screen">
    <h1 class="text-2xl font-bold mb-4">Manajemen Pengguna</h1>

    <!-- Tombol Tambah User -->
    <button
      class="mb-4 px-4 py-2 bg-blue-500 text-white rounded"
      @click="openModal('add')"
    >
      Tambah Pengguna
    </button>

    <!-- Tabel User -->
    <table class="w-full border-collapse border border-gray-300">
      <thead>
        <tr class="bg-gray-200">
          <th class="border border-gray-300 px-4 py-2">Nama</th>
          <th class="border border-gray-300 px-4 py-2">Email</th>
          <th class="border border-gray-300 px-4 py-2">Jabatan</th>
          <th class="border border-gray-300 px-4 py-2">Foto</th>
          <th class="border border-gray-300 px-4 py-2">Aksi</th>
        </tr>
      </thead>
      <tbody>
        <tr
          v-for="(user, index) in users"
          :key="index"
          class="border border-gray-300"
        >
          <td class="border border-gray-300 px-4 py-2">{{ user.name }}</td>
          <td class="border border-gray-300 px-4 py-2">{{ user.email }}</td>
          <td class="border border-gray-300 px-4 py-2">{{ user.position }}</td>
          <td class="border border-gray-300 px-4 py-2">
            <img :src="user.photo" alt="Foto" class="w-12 h-12 rounded-full" />
          </td>
          <td class="border border-gray-300 px-4 py-2">
            <button
              class="bg-yellow-500 text-white px-2 py-1 rounded mr-2"
              @click="openModal('edit', user, index)"
            >
              Edit
            </button>
            <button
              class="bg-red-500 text-white px-2 py-1 rounded"
              @click="deleteUser(index)"
            >
              Hapus
            </button>
          </td>
        </tr>
      </tbody>
    </table>

    <!-- Modal Tambah/Edit User -->
    <div
      v-if="isModalOpen"
      class="fixed inset-0 flex items-center justify-center bg-gray-900 bg-opacity-50"
    >
      <div class="bg-white p-6 rounded-lg w-96">
        <h2 class="text-xl font-bold mb-4">
          {{ isEdit ? "Edit Pengguna" : "Tambah Pengguna" }}
        </h2>
        <label class="block mb-2">Nama Lengkap:</label>
        <input
          type="text"
          v-model="form.name"
          class="w-full px-3 py-2 border rounded mb-3"
        />
        <label class="block mb-2">Email:</label>
        <input
          type="email"
          v-model="form.email"
          class="w-full px-3 py-2 border rounded mb-3"
        />
        <label class="block mb-2">Jabatan:</label>
        <input
          type="text"
          v-model="form.position"
          class="w-full px-3 py-2 border rounded mb-3"
        />
        <label class="block mb-2">Foto URL:</label>
        <input
          type="text"
          v-model="form.photo"
          class="w-full px-3 py-2 border rounded mb-3"
        />

        <div class="flex justify-end space-x-2">
          <button
            class="px-4 py-2 bg-gray-400 text-white rounded"
            @click="isModalOpen = false"
          >
            Batal
          </button>
          <button
            class="px-4 py-2 bg-green-500 text-white rounded"
            @click="isEdit ? updateUser() : addUser()"
          >
            {{ isEdit ? "Simpan" : "Tambah" }}
          </button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import { ref } from "vue";

export default {
  setup() {
    const users = ref([
      {
        name: "John Doe",
        email: "john@example.com",
        position: "Manager",
        photo: "https://via.placeholder.com/50",
      },
      {
        name: "Jane Doe",
        email: "jane@example.com",
        position: "Developer",
        photo: "https://via.placeholder.com/50",
      },
    ]);
    const isModalOpen = ref(false);
    const isEdit = ref(false);
    const form = ref({ name: "", email: "", position: "", photo: "" });
    const currentIndex = ref(null);

    const openModal = (type, user = null, index = null) => {
      isEdit.value = type === "edit";
      isModalOpen.value = true;
      if (user) {
        form.value = { ...user };
        currentIndex.value = index;
      } else {
        form.value = { name: "", email: "", position: "", photo: "" };
      }
    };

    const addUser = () => {
      users.value.push({ ...form.value });
      isModalOpen.value = false;
    };

    const updateUser = () => {
      if (currentIndex.value !== null) {
        users.value[currentIndex.value] = { ...form.value };
      }
      isModalOpen.value = false;
    };

    const deleteUser = (index) => {
      users.value.splice(index, 1);
    };

    return {
      users,
      isModalOpen,
      isEdit,
      form,
      openModal,
      addUser,
      updateUser,
      deleteUser,
    };
  },
};
</script>

<style>
body {
  font-family: Arial, sans-serif;
}
</style>
