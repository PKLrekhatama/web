<template>
  <div class="con min-h-screen pt-5">
    <div class="bg-white rounded-r-lg p-4 w-52 tag">
      <div class="w-full flex items-center justify-center">
        <h1 class="font-bold">Training & Certification</h1>
      </div>
    </div>
    <div class="container text-black mx-auto p-4">
      <div
        class="flex flex-col md:flex-row mb-8"
        data-aos="fade-up"
        data-aos-anchor-placement="top-bottom"
      >
        <div class="md:w-1/2 p-4">
          <img
            alt="Illustration of a digital ecosystem"
            class="w-full rounded-lg shadow-lg"
            src="https://placehold.co/600x400"
          />
        </div>
        <div
          class="md:w-1/2 p-4"
        >
          <h3 class="text-xl font-bold mb-4">Apa yang kami berikan?</h3>
          <p class="mb-4">
            Rekhalista adalah penyedia layanan Teknologi Informasi dan
            Non-Teknologi informasi yang berkomitmen untuk membantu semua
            stakeholders yang terlibat dalam pengembangan ekosistem yang sesuai
            dengan kebutuhan bisnis mereka. Beberapa layanan yang kami berikan:
          </p>
          <ul
            class="list-disc list-inside mb-4  font-semibold"
            data-aos="fade-up"
            data-aos-anchor-placement="bottom-bottom"
          >
            <li class="menu-item">
                <a href="/category/ITManagement%26service">
                    IT Magement & Service
                </a>
            </li>
            <li class="menu-item">
              <a href="/category/ITNextGeneration">
                IT Next Generation
              </a>
            </li>
            <li class="menu-item">
              <a href="/category/BigData">
                Big Data
              </a>
            </li>
            <li class="menu-item">
              <a href="/category/serverAdministration">
                Server Administration
              </a>
            </li>
            <li class="menu-item">
                <a href="/category/DataBase">
                    Database
                </a>
            </li>
            <li class="menu-item">
                <a href="/category/programming">
                    Programming
                </a>
            </li>
            <li class="menu-item">
                <a href="/category/network%26Security">Network & Security</a>
            </li>
            <li class="menu-item">
                <a href="/category/design&Animation">Design & Animation</a>
            </li>
            <li class="menu-item">
                <a href="category/ITFundamental">IT Fundamental</a>
            </li>
            <li class="menu-item">
                <a href="/category/cloudComputing">Cloud Computing</a>
            </li>
            <li class="menu-item">
                <a href="/category/other&NonIT">Other & Non IT</a>
            </li>
          </ul>
        </div>
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
.menu-item a {
  color: #000000;
  text-decoration: none;
  transition: color 0.2s ease-in-out;
}

.menu-item:hover a {
  color: #007bff; /* Ubah warna teks saat hover */
}
</style>
