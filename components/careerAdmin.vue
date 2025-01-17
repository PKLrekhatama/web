<template>
    <div class="container mx-auto p-6 bg-gray-100 h-screen">
      <h1 class="text-2xl font-bold mb-4">Manajemen Career</h1>
      
      <!-- Tombol Tambah Artikel -->
      <button 
        class="mb-4 px-4 py-2 bg-blue-500 text-white rounded" 
        @click="openModal('add')">
        Tambah Career
      </button>
      
      <!-- Tabel Artikel -->
      <table class="w-full border-collapse border border-gray-300">
        <thead>
          <tr class="bg-gray-200">
            <th class="border border-gray-300 px-4 py-2">Foto</th>
            <th class="border border-gray-300 px-4 py-2">Judul</th>
            <th class="border border-gray-300 px-4 py-2">Keterangan</th>
            <th class="border border-gray-300 px-4 py-2">Aksi</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="(article, index) in articles" :key="index" class="border border-gray-300">
            <td class="border border-gray-300 px-4 py-2">
              <img v-if="article.photo" :src="article.photo" alt="Foto" class="w-16 h-16 object-cover rounded">
            </td>
            <td class="border border-gray-300 px-4 py-2">{{ article.title }}</td>
            <td class="border border-gray-300 px-4 py-2">{{ article.description }}</td>
            <td class="border border-gray-300 px-4 py-2">
              <button class="bg-yellow-500 text-white px-2 py-1 rounded mr-2" @click="openModal('edit', article, index)">Edit</button>
              <button class="bg-red-500 text-white px-2 py-1 rounded" @click="deleteArticle(index)">Hapus</button>
            </td>
          </tr>
        </tbody>
      </table>
  
      <!-- Modal Tambah/Edit Artikel -->
      <div v-if="isModalOpen" class="fixed inset-0 flex items-center justify-center bg-gray-900 bg-opacity-50">
        <div class="bg-white p-6 rounded-lg w-96">
          <h2 class="text-xl font-bold mb-4">{{ isEdit ? 'Edit Artikel' : 'Tambah Artikel' }}</h2>
          <label class="block mb-2">Foto (Opsional):</label>
          <input type="text" v-model="form.photo" placeholder="Masukkan URL Foto" class="w-full px-3 py-2 border rounded mb-3" />
          <label class="block mb-2">Judul Artikel:</label>
          <input type="text" v-model="form.title" class="w-full px-3 py-2 border rounded mb-3" />
          <label class="block mb-2">Keterangan:</label>
          <textarea v-model="form.description" class="w-full px-3 py-2 border rounded mb-3"></textarea>
          
          <div class="flex justify-end space-x-2">
            <button class="px-4 py-2 bg-gray-400 text-white rounded" @click="isModalOpen = false">Batal</button>
            <button class="px-4 py-2 bg-green-500 text-white rounded" @click="isEdit ? updateArticle() : addArticle()">
              {{ isEdit ? 'Simpan' : 'Tambah' }}
            </button>
          </div>
        </div>
      </div>
    </div>
  </template>
  
  <script>
  import { ref } from 'vue';
  
  export default {
    setup() {
      const articles = ref([
        { title: 'Career Pertama', description: 'Ini adalah deskripsi Career pertama.', photo: '' },
        { title: 'Career Kedua', description: 'Ini adalah deskripsi Career kedua.', photo: 'https://via.placeholder.com/150' }
      ]);
      const isModalOpen = ref(false);
      const isEdit = ref(false);
      const form = ref({ photo: '', title: '', description: '' });
      const currentIndex = ref(null);
  
      const openModal = (type, article = null, index = null) => {
        isEdit.value = type === 'edit';
        isModalOpen.value = true;
        if (article) {
          form.value = { ...article };
          currentIndex.value = index;
        } else {
          form.value = { photo: '', title: '', description: '' };
        }
      };
  
      const addArticle = () => {
        articles.value.push({ ...form.value });
        isModalOpen.value = false;
      };
  
      const updateArticle = () => {
        if (currentIndex.value !== null) {
          articles.value[currentIndex.value] = { ...form.value };
        }
        isModalOpen.value = false;
      };
  
      const deleteArticle = (index) => {
        articles.value.splice(index, 1);
      };
  
      return {
        articles,
        isModalOpen,
        isEdit,
        form,
        openModal,
        addArticle,
        updateArticle,
        deleteArticle
      };
    }
  };
  </script>
  
  <style>
  body {
    font-family: Arial, sans-serif;
  }
  </style>
  