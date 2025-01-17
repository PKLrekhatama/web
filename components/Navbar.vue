<template>
  <nav
    class="bg-gray-800 bg-opacity-50 backdrop-blur-lg sticky top-0 border-b-lg text-black"
  >
    <div class="mx-auto max-w-7xl px-2 sm:px-6 lg:px-8">
      <div class="relative flex h-16 items-center justify-between">
        <!-- Mobile Menu Button -->
        <div class="absolute inset-y-0 left-0 flex items-center sm:hidden">
          <button
            @click="toggleMobileMenu"
            type="button"
            class="relative inline-flex items-center justify-center rounded-md p-2 text-black hover:bg-gray-700 hover:text-white focus:outline-none focus:ring-2 focus:ring-inset focus:ring-white"
            aria-controls="mobile-menu"
            :aria-expanded="isMobileMenuOpen"
          >
            <span class="sr-only">Open main menu</span>
            <!-- Icon: Closed Menu -->
            <svg
              v-if="!isMobileMenuOpen"
              class="block h-6 w-6"
              xmlns="http://www.w3.org/2000/svg"
              fill="none"
              viewBox="0 0 24 24"
              stroke-width="1.5"
              stroke="currentColor"
              aria-hidden="true"
            >
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                d="M3.75 6.75h16.5M3.75 12h16.5m-16.5 5.25h16.5"
              />
            </svg>
            <!-- Icon: Open Menu -->
            <svg
              v-else
              class="block h-6 w-6"
              xmlns="http://www.w3.org/2000/svg"
              fill="none"
              viewBox="0 0 24 24"
              stroke-width="1.5"
              stroke="currentColor"
              aria-hidden="true"
            >
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                d="M6 18 18 6M6 6l12 12"
              />
            </svg>
          </button>
        </div>

        <!-- Logo and Desktop Navigation -->
        <div
          class="flex flex-1 items-center justify-center sm:items-stretch sm:justify-start"
        >
          <div class="flex shrink-0 items-center">
            <a href="/admin/login/">
              <img
                class="h-8 w-auto"
                src="/assets/img/Logo.png"
                alt="Your Company"
              />
            </a>
          </div>
          <div class="hidden sm:ml-6 sm:block">
            <div class="flex space-x-4">
              <a
                href="/"
                class="rounded-md px-3 py-2 text-sm font-medium text-black hover:bg-gray-700 hover:text-white"
                aria-current="page"
              >
                Home
              </a>
              <a
                href="/store"
                class="rounded-md px-3 py-2 text-sm font-medium text-black hover:bg-gray-700 hover:text-black"
              >
                Store
              </a>
              <!-- Dropdown Menus -->
              <div
                v-for="(menu, index) in dropdownMenus"
                :key="index"
                class="relative text-left"
              >
                <button
                  @click="toggleDropdown(index)"
                  type="button"
                  class="flex items-center rounded-md px-3 py-2 text-sm font-medium text-black hover:bg-gray-700 hover:text-white"
                  id="menu-button"
                  :aria-expanded="
                    openDropdownIndex === index ? 'true' : 'false'
                  "
                  aria-haspopup="true"
                >
                  {{ menu.name }}
                  <svg
                    class="ml-2 h-4 w-4 text-black"
                    viewBox="0 0 20 20"
                    fill="currentColor"
                    aria-hidden="true"
                  >
                    <path
                      fill-rule="evenodd"
                      d="M5.22 8.22a.75.75 0 0 1 1.06 0L10 11.94l3.72-3.72a.75.75 0 1 1 1.06 1.06l-4.25 4.25a.75.75 0 0 1-1.06 0L5.22 9.28a.75.75 0 0 1 0-1.06Z"
                      clip-rule="evenodd"
                    />
                  </svg>
                </button>

                <!-- Dropdown menu -->
                <div
                  v-if="openDropdownIndex === index"
                  class="absolute z-10 mt-2 w-56 origin-top-right rounded-md bg-white shadow-lg ring-1 ring-black/5 focus:outline-none"
                  role="menu"
                  aria-orientation="vertical"
                  aria-labelledby="menu-button"
                  tabindex="-1"
                >
                  <div class="py-1" role="none">
                    <a
                      v-for="(item, i) in menu.items"
                      :key="i"
                      :href="item.url"
                      class="block px-4 py-2 text-sm text-black hover:bg-gray-100"
                      role="menuitem"
                    >
                      {{ item.label }}
                    </a>
                  </div>
                </div>
              </div>
              <!-- End Dropdown Menus -->
              <a
                href="/contactUs"
                class="rounded-md px-3 py-2 text-sm font-medium text-black-300 hover:bg-gray-700 hover:text-white"
              >
                Contact Us
              </a>
            </div>
          </div>
        </div>

        <!-- Profile Dropdown -->
        <div class="relative ml-3">
          <button
            @click="toggleProfileDropdown"
            type="button"
            class="relative flex text-sm"
          >
            <span class="sr-only">Open user menu</span>
            <ion-icon
              name="menu-outline"
              style="font-size: 1.5rem; color: rgb(113, 171, 72)"
            ></ion-icon>
          </button>
          <transition
            name="dropdown"
            enter-active-class="transition ease-out duration-200"
            leave-active-class="transition ease-in duration-150"
          >
            <div
              v-if="isProfileDropdownOpen"
              class="absolute right-0 z-50 mt-2 w-48 origin-top-right rounded-md bg-white py-1 shadow-lg ring-1 ring-black/5"
              role="menu"
              aria-orientation="vertical"
            >
              <button type="button" style="width: 100%" disabled>
                <a
                  href="#"
                  class="block px-4 py-2 text-sm text-gray-700"
                  role="menuitem"
                >
                  Training Category
                </a>
              </button>
              <hr style="height: 5px; color: greenyellow" />
              <a
                href="/category/ITManagement%26service/"
                class="block px-4 py-2 text-sm text-gray-700 hover:bg-gray-100"
                role="menuitem"
              >
                IT Management & Service
              </a>
              <a
                href="/category/ITNextGeneration/"
                class="block px-4 py-2 text-sm text-gray-700 hover:bg-gray-100"
                role="menuitem"
              >
                IT Next Generation
              </a>
              <a
                href="/category/BigData/"
                class="block px-4 py-2 text-sm text-gray-700 hover:bg-gray-100"
                role="menuitem"
              >
                Big Data
              </a>
              <a
                href="/category/serverAdministration/"
                class="block px-4 py-2 text-sm text-gray-700 hover:bg-gray-100"
                role="menuitem"
              >
                Server Administration
              </a>
              <a
                href="/category/DataBase/"
                class="block px-4 py-2 text-sm text-gray-700 hover:bg-gray-100"
                role="menuitem"
              >
                Database
              </a>
              <a
                href="/category/programming/"
                class="block px-4 py-2 text-sm text-gray-700 hover:bg-gray-100"
                role="menuitem"
              >
                Programming
              </a>
              <a
                href="/category/network%26Security/"
                class="block px-4 py-2 text-sm text-gray-700 hover:bg-gray-100"
                role="menuitem"
              >
                Network & Security
              </a>
              <a
                href="/category/design%26Animation/"
                class="block px-4 py-2 text-sm text-gray-700 hover:bg-gray-100"
                role="menuitem"
              >
                Design & Animation
              </a>
              <a
                href="/category/ITFundamental/"
                class="block px-4 py-2 text-sm text-gray-700 hover:bg-gray-100"
                role="menuitem"
              >
                IT Fundamental
              </a>
              <a
                href="/category/cloudComputing/"
                class="block px-4 py-2 text-sm text-gray-700 hover:bg-gray-100"
                role="menuitem"
              >
                Cloud Computing
              </a>
              <a
                href="/category/other%26NonIT/"
                class="block px-4 py-2 text-sm text-gray-700 hover:bg-gray-100"
                role="menuitem"
              >
                Other & Non IT
              </a>
            </div>
          </transition>
        </div>
      </div>
    </div>

    <!-- Mobile Menu -->
    <transition
      name="mobile-menu"
      enter-active-class="transition ease-out duration-200"
      leave-active-class="transition ease-in duration-150"
    >
      <div v-if="isMobileMenuOpen" class="sm:hidden" id="mobile-menu">
        <div class="space-y-1 px-2 pb-3 pt-2">
          <a
            href="/"
            class="block rounded-md px-3 py-2 text-base font-medium text-black hover:bg-gray-700 hover:text-white"
            aria-current="page"
          >
            Home
          </a>
          <div
            v-for="(menu, index) in dropdownMenus"
            :key="index"
            class="relative text-left"
          >
            <button
              @click="toggleDropdown(index)"
              type="button"
              class="flex items-center rounded-md px-3 py-2 text-sm font-medium text-black hover:bg-gray-700 hover:text-white"
              id="menu-button"
              :aria-expanded="openDropdownIndex === index ? 'true' : 'false'"
              aria-haspopup="true"
            >
              {{ menu.name }}
              <svg
                class="ml-2 h-4 w-4 text-black"
                viewBox="0 0 20 20"
                fill="currentColor"
                aria-hidden="true"
              >
                <path
                  fill-rule="evenodd"
                  d="M5.22 8.22a.75.75 0 0 1 1.06 0L10 11.94l3.72-3.72a.75.75 0 1 1 1.06 1.06l-4.25 4.25a.75.75 0 0 1-1.06 0L5.22 9.28a.75.75 0 0 1 0-1.06Z"
                  clip-rule="evenodd"
                />
              </svg>
            </button>

            <!-- Dropdown menu -->
            <div
              v-if="openDropdownIndex === index"
              class="absolute z-10 mt-2 w-56 origin-top-right rounded-md bg-white shadow-lg ring-1 ring-black/5 focus:outline-none"
              role="menu"
              aria-orientation="vertical"
              aria-labelledby="menu-button"
              tabindex="-1"
            >
              <div class="py-1" role="none">
                <a
                  v-for="(item, i) in menu.items"
                  :key="i"
                  :href="item.url"
                  class="block px-4 py-2 text-sm text-gray-700 hover:bg-gray-100"
                  role="menuitem"
                >
                  {{ item.label }}
                </a>
              </div>
            </div>
          </div>
          <a
            href="/contactUs"
            class="flex items-center rounded-md px-3 py-2 text-sm font-medium text-black hover:bg-gray-700 hover:text-white"
          >
            Contact Us
          </a>
        </div>
      </div>
    </transition>
  </nav>
</template>

<script>
export default {
  data() {
    return {
      isMobileMenuOpen: false,
      openDropdownIndex: null,
      isProfileDropdownOpen: false,
      dropdownMenus: [
        {
          name: "Our Service",
          items: [
            {
              label: "Training & Certification",
              url: "../service/training%26certification",
            },
            { label: "Consultan", url: "../service/consultan" },
            {
              label: "Software Development",
              url: "/service/softwareDevelopment",
            },
            {
              label: "Rekhatama Educator",
              url: "https://www.learn.rekhatama.com/",
            },
          ],
        },
        {
          name: "News",
          items: [
            { label: "Article", url: "/news/article/" },
            { label: "Event", url: "/news/event/" },
            { label: "Career", url: "/news/career/" },
          ],
        },
        {
          name: "About Us",
          items: [
            { label: "Rekhatama", url: "/aboutUs/rekhatama" },
            { label: "Our Teams", url: "/aboutUs/ourTeams" },
          ],
        },
      ],
    };
  },
  methods: {
    toggleMobileMenu() {
      this.isMobileMenuOpen = !this.isMobileMenuOpen;
    },
    toggleDropdown(index) {
      if (this.openDropdownIndex === index) {
        this.openDropdownIndex = null;
      } else {
        this.openDropdownIndex = index;
      }
    },
    toggleProfileDropdown() {
      this.isProfileDropdownOpen = !this.isProfileDropdownOpen;
    },
  },
};
</script>

<style scoped>
/* Dropdown animation */
.dropdown-enter-active,
.dropdown-leave-active {
  transition: opacity 0.2s ease, transform 0.2s ease;
}
.dropdown-enter-from,
.dropdown-leave-to {
  opacity: 0;
  transform: scale(0.95);
}

/* Mobile menu animation */
.mobile-menu-enter-active,
.mobile-menu-leave-active {
  transition: opacity 0.3s ease;
}
.mobile-menu-enter-from,
.mobile-menu-leave-to {
  opacity: 0;
}
Nav {
  backdrop-filter: blur(10px);
  -webkit-backdrop-filter: blur(10px);
  background-color: rgba(
    255,
    255,
    255,
    0.7
  ); /* Tailwind: bg-gray-800 bg-opacity-50 */
  z-index: 2;
}

.mobile-menu div {
  position: relative;
  z-index: 50;
}

.dropdown-menu {
  position: absolute; /* Pastikan dropdown berada dalam konteks relatif */
  left: 0; /* Atur posisi horizontal */
  top: 100%; /* Letakkan dropdown di bawah tombol */
  z-index: 50; /* Pastikan dropdown muncul di atas elemen lain */
  background-color: white;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
  padding: 0.5rem; /* Beri jarak padding internal */
  width: 100%; /* Pastikan dropdown selebar tombol pada mobile */
}

.mobile-menu {
  position: relative; /* Kontainer harus memiliki posisi relatif */
}

.dropdown-menu a {
  display: block; /* Setiap item dalam dropdown menjadi satu baris */
  padding: 0.5rem 1rem;
  text-decoration: none;
  color: #333;
}

.dropdown-menu a:hover {
  background-color: #f3f4f6;
}
</style>
