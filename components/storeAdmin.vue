<template>
  <div class="min-h-screen p-6 bg-gray-100">
    <!-- Header -->
    <div class="bg-white p-4 shadow-md rounded-lg mb-6">
      <h1 class="text-2xl font-bold text-gray-800 text-center">Store</h1>
    </div>

    <!-- Tombol Tambah Produk -->
    <div class="mb-4 flex justify-center">
      <button
        class="bg-blue-600 text-white px-4 py-2 rounded-md hover:bg-blue-700 transition"
        @click="openForm(null)"
      >
        Tambah Produk
      </button>
    </div>

    <!-- Form Tambah/Edit Produk -->
    <div
      v-if="showForm"
      class="bg-white p-6 rounded-lg shadow-md max-w-lg mx-auto"
    >
      <h2 class="text-lg font-bold text-gray-800 mb-4">
        {{ editIndex === null ? "Tambah Produk" : "Edit Produk" }}
      </h2>

      <div class="mb-4">
        <label class="block text-gray-700">Nama Produk:</label>
        <input
          v-model="newProduct.name"
          type="text"
          class="w-full p-2 border rounded-md"
        />
      </div>

      <div class="mb-4">
        <label class="block text-gray-700">Keterangan Produk:</label>
        <textarea
          v-model="newProduct.description"
          class="w-full p-2 border rounded-md"
        ></textarea>
      </div>

      <div class="mb-4">
        <label class="block text-gray-700">Harga:</label>
        <input
          v-model="newProduct.price"
          type="number"
          class="w-full p-2 border rounded-md"
        />
      </div>

      <div class="flex justify-between">
        <button
          class="bg-green-600 text-white px-4 py-2 rounded-md hover:bg-green-700 transition"
          @click="saveProduct"
        >
          {{ editIndex === null ? "Simpan" : "Update" }}
        </button>
        <button
          class="bg-red-600 text-white px-4 py-2 rounded-md hover:bg-red-700 transition"
          @click="cancelEdit"
        >
          Batal
        </button>
      </div>
    </div>

    <!-- Daftar Produk -->
    <div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 gap-6 mt-6">
      <div
        v-for="(product, index) in products"
        :key="index"
        class="bg-white p-4 rounded-lg shadow-md"
      >
        <h3 class="text-lg font-semibold text-gray-800">{{ product.name }}</h3>
        <p class="text-gray-600 text-sm">{{ product.description }}</p>
        <p class="text-gray-800 font-medium mt-2">
          Harga: Rp {{ formatPrice(product.price) }}
        </p>
        <div class="mt-4 flex space-x-2">
          <button
            class="bg-yellow-500 text-white px-3 py-1 rounded-md hover:bg-yellow-600 transition"
            @click="openForm(index)"
          >
            Edit
          </button>
          <button
            class="bg-red-500 text-white px-3 py-1 rounded-md hover:bg-red-600 transition"
            @click="deleteProduct(index)"
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
      showForm: false, // Kontrol tampilan form
      editIndex: null, // Untuk melacak apakah sedang edit atau tambah
      newProduct: { name: "", description: "", price: "" }, // Data produk baru
      products: [
        {
          name: "Laptop Gaming",
          description: "Laptop untuk gaming dan kerja berat.",
          price: 15000000,
        },
        {
          name: "Smartphone 5G",
          description: "Ponsel dengan jaringan 5G terbaru.",
          price: 8000000,
        },
        {
          name: "Headphone ANC",
          description: "Headphone dengan peredam bising.",
          price: 2500000,
        },
      ], // Produk bawaan
    };
  },
  methods: {
    openForm(index) {
      if (index !== null) {
        // Mode Edit
        this.editIndex = index;
        this.newProduct = { ...this.products[index] };
      } else {
        // Mode Tambah
        this.editIndex = null;
        this.newProduct = { name: "", description: "", price: "" };
      }
      this.showForm = true;
    },
    saveProduct() {
      if (
        !this.newProduct.name ||
        !this.newProduct.description ||
        !this.newProduct.price
      ) {
        alert("Semua field harus diisi!");
        return;
      }

      if (this.editIndex === null) {
        // Tambah produk baru
        this.products.push({ ...this.newProduct });
      } else {
        // Update produk yang sudah ada
        this.products[this.editIndex] = { ...this.newProduct };
      }

      this.cancelEdit();
    },
    deleteProduct(index) {
      if (confirm("Apakah Anda yakin ingin menghapus produk ini?")) {
        this.products.splice(index, 1);
      }
    },
    cancelEdit() {
      this.showForm = false;
      this.editIndex = null;
      this.newProduct = { name: "", description: "", price: "" };
    },
    formatPrice(value) {
      return new Intl.NumberFormat("id-ID").format(value);
    },
  },
};
</script>

<style scoped>
input,
textarea {
  border: 1px solid #ccc;
}
</style>
