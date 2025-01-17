<template>
    <div class="min-h-screen p-6 bg-gray-100">
      <!-- Header -->
      <div class="bg-white p-4 shadow-md rounded-lg mb-6">
        <h1 class="text-2xl font-bold text-gray-800 text-center">Manajemen Kategori</h1>
      </div>

      <!-- Tombol Tambah Kategori -->
      <div class="mb-4 flex justify-center">
        <button
          class="bg-blue-600 text-white px-4 py-2 rounded-md hover:bg-blue-700 transition"
          @click="openForm(null)"
        >
          Tambah Kategori
        </button>
      </div>

      <!-- Form Tambah/Edit Kategori -->
      <div v-if="showForm" class="bg-white p-6 rounded-lg shadow-md max-w-lg mx-auto">
        <h2 class="text-lg font-bold text-gray-800 mb-4">{{ editIndex === null ? 'Tambah Kategori' : 'Edit Kategori' }}</h2>

        <div class="mb-4">
          <label class="block text-gray-700">Nama Kategori:</label>
          <input v-model="newCategory.name" type="text" class="w-full p-2 border rounded-md">
        </div>

        <div class="mb-4">
          <label class="block text-gray-700">Keterangan:</label>
          <textarea v-model="newCategory.description" class="w-full p-2 border rounded-md"></textarea>
        </div>

        <div class="mb-4">
          <label class="block text-gray-700">Jenis Kategori:</label>
          <select v-model="newCategory.type" class="w-full p-2 border rounded-md">
            <option v-for="option in categoryOptions" :key="option" :value="option">
              {{ option }}
            </option>
          </select>
        </div>

        <div class="flex justify-between">
          <button
            class="bg-green-600 text-white px-4 py-2 rounded-md hover:bg-green-700 transition"
            @click="saveCategory"
          >
            {{ editIndex === null ? 'Simpan' : 'Update' }}
          </button>
          <button
            class="bg-red-600 text-white px-4 py-2 rounded-md hover:bg-red-700 transition"
            @click="cancelEdit"
          >
            Batal
          </button>
        </div>
      </div>

      <!-- Daftar Kategori -->
      <div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 gap-6 mt-6">
        <div
          v-for="(category, index) in categories"
          :key="index"
          class="bg-white p-4 rounded-lg shadow-md flex flex-col justify-between"
        >
          <h3 class="text-lg font-bold text-gray-800 mb-2">{{ category.name }}</h3>
          <p class="text-gray-800 text-sm mb-2"><b>Keterangan:</b> {{ category.description }}</p>
          <p class="text-gray-800 text-sm"><b>Jenis:</b> {{ category.type }}</p>

          <div class="mt-4 flex space-x-2">
            <button
              class="bg-yellow-500 text-white px-3 py-1 rounded-md hover:bg-yellow-600 transition"
              @click="openForm(index)"
            >
              Edit
            </button>
            <button
              class="bg-red-500 text-white px-3 py-1 rounded-md hover:bg-red-600 transition"
              @click="deleteCategory(index)"
            >
              Hapus
            </button>
          </div>
        </div>
      </div>
    </div>
</template>

<script>
export default {
  data() {
    return {
      showForm: false, // Menampilkan atau menyembunyikan form
      editIndex: null, // Menentukan apakah sedang mengedit kategori
      newCategory: { name: "", description: "", type: "IT Management & Service" }, // Data kategori baru
      categories: [
        { name: "IT Management", description: "Manajemen layanan IT dan strategi bisnis", type: "IT Management & Service" },
        { name: "Big Data", description: "Analisis data skala besar", type: "Big Data" },
        { name: "Design & Animation", description: "Pembuatan desain grafis dan animasi", type: "Design & Animation" },
      ], // Data kategori awal
      categoryOptions: [
        "IT Management & Service",
        "IT Next Generation",
        "Big Data",
        "Server Administration",
        "Database",
        "Programming",
        "Network & Security",
        "Design & Animation",
        "IT Fundamental",
        "Cloud Computing",
        "Other & Non IT",
      ], // Pilihan kategori sesuai gambar
    };
  },
  methods: {
    openForm(index) {
      if (index !== null) {
        // Mode Edit
        this.editIndex = index;
        this.newCategory = { ...this.categories[index] };
      } else {
        // Mode Tambah
        this.editIndex = null;
        this.newCategory = { name: "", description: "", type: "IT Management & Service" };
      }
      this.showForm = true;
    },
    saveCategory() {
      if (!this.newCategory.name || !this.newCategory.description) {
        alert("Nama dan Keterangan kategori tidak boleh kosong!");
        return;
      }

      if (this.editIndex === null) {
        // Tambah kategori baru
        this.categories.push({ ...this.newCategory });
      } else {
        // Edit kategori yang ada
        this.categories[this.editIndex] = { ...this.newCategory };
      }

      this.cancelEdit();
    },
    deleteCategory(index) {
      if (confirm("Apakah Anda yakin ingin menghapus kategori ini?")) {
        this.categories.splice(index, 1);
      }
    },
    cancelEdit() {
      this.showForm = false;
      this.editIndex = null;
      this.newCategory = { name: "", description: "", type: "IT Management & Service" };
    },
  },
};
</script>

<style scoped>
input, textarea, select {
  border: 1px solid #ccc;
}
</style>
