<script setup lang="ts">
import { vOnClickOutside } from "@vueuse/components";
const props = defineProps<{ toggler: Boolean; direction: "right" | "left" }>();

const emit = defineEmits<{
  (e: "handleclickOutside"): void;
}>();

function handleClickOutside() {
  if (props.toggler) {
    emit("handleclickOutside");
  }
}
</script>

<template>
  <aside
    class="w-64 bg-white h-screen shadow-md flex flex-col justify-between z-10 fixed top-0 transform transition-transform duration-300 ease-in-out"
    v-on-click-outside="handleClickOutside"
    :class="[
      direction === 'right' ? 'right-0' : 'left-0',
      toggler
        ? 'translate-x-0'
        : direction === 'right'
        ? 'translate-x-[99rem]'
        : '-translate-x-96',
    ]"
  >
    <div class="p-6">
      <h1 class="text-xl font-bold mb-4">Chatbot Dashboard</h1>
      <nav class="space-y-2">
        <a
          href="#"
          class="flex items-center p-2 text-gray-700 hover:bg-gray-100 rounded"
        >
          <span class="mr-3">
            <!-- Home Icon -->
            <svg
              xmlns="http://www.w3.org/2000/svg"
              class="h-5 w-5"
              fill="none"
              viewBox="0 0 24 24"
              stroke="currentColor"
            >
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                d="M3 9.5L12 3l9 6.5v9.5a2 2 0 01-2 2h-4a2 2 0 01-2-2v-4H9v4a2 2 0 01-2 2H3a2 2 0 01-2-2V9.5z"
              />
            </svg>
          </span>
          <span>My Chatbots</span>
        </a>
        <a
          href="#"
          class="flex items-center p-2 text-gray-700 hover:bg-gray-100 rounded"
        >
          <span class="mr-3">
            <!-- View Icon -->
            <svg
              xmlns="http://www.w3.org/2000/svg"
              class="h-5 w-5"
              fill="none"
              viewBox="0 0 24 24"
              stroke="currentColor"
            >
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                d="M15 12l-3-3m0 0l-3 3m3-3v12M5 12a7 7 0 0114 0v4a2 2 0 01-2 2H7a2 2 0 01-2-2v-4z"
              />
            </svg>
          </span>
          <span>View Chatbot</span>
        </a>
        <a
          href="#"
          class="flex items-center p-2 text-gray-700 hover:bg-gray-100 rounded"
        >
          <span class="mr-3">
            <!-- Analytics Icon -->
            <svg
              xmlns="http://www.w3.org/2000/svg"
              class="h-5 w-5"
              fill="none"
              viewBox="0 0 24 24"
              stroke="currentColor"
            >
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                d="M11 3a8 8 0 0116 0v7a8 8 0 01-16 0V3zm5 15h-4v7h4v-7zm-9 3h4v-3H7v3zm-4 3h4v-5H3v5z"
              />
            </svg>
          </span>
          <span>Analytics</span>
        </a>
        <a
          href="#"
          class="flex items-center p-2 text-gray-700 hover:bg-gray-100 rounded"
        >
          <span class="mr-3">
            <!-- Messages Icon -->
            <svg
              xmlns="http://www.w3.org/2000/svg"
              class="h-5 w-5"
              fill="none"
              viewBox="0 0 24 24"
              stroke="currentColor"
            >
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                d="M3 5a3 3 0 013-3h12a3 3 0 013 3v10a3 3 0 01-3 3H9l-6 3V5z"
              />
            </svg>
          </span>
          <span>Messages</span>
        </a>
        <a
          href="#"
          class="flex items-center p-2 text-gray-700 hover:bg-gray-100 rounded"
        >
          <span class="mr-3">
            <!-- Leads Icon -->
            <svg
              xmlns="http://www.w3.org/2000/svg"
              class="h-5 w-5"
              fill="none"
              viewBox="0 0 24 24"
              stroke="currentColor"
            >
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                d="M12 4.354c-4.418 0-8 1.79-8 4v7.99a3 3 0 003 3h2m3 0h6a3 3 0 003-3V8.354c0-2.21-3.582-4-8-4zM12 1v3M9.879 5.879l-2.121 2.122M4 9h3M20 9h-3M14.121 5.879l2.122 2.122"
              />
            </svg>
          </span>
          <span>Leads</span>
        </a>
        <hr class="my-2 border-gray-300" />
        <a
          href="#"
          class="flex items-center p-2 text-gray-700 bg-gray-100 rounded"
        >
          <span class="mr-3">
            <!-- Training Icon -->
            <svg
              xmlns="http://www.w3.org/2000/svg"
              class="h-5 w-5"
              fill="none"
              viewBox="0 0 24 24"
              stroke="currentColor"
            >
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                d="M7 20h10M12 4v16m0 0H8m4 0h4"
              />
            </svg>
          </span>
          <span>Training Sources</span>
        </a>
        <a
          href="#"
          class="flex items-center p-2 text-gray-700 hover:bg-gray-100 rounded"
        >
          <span class="mr-3">
            <!-- Visual Look Icon -->
            <svg
              xmlns="http://www.w3.org/2000/svg"
              class="h-5 w-5"
              fill="none"
              viewBox="0 0 24 24"
              stroke="currentColor"
            >
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                d="M15 12h4m-4-2h6m-6 4h6m-6 4h4M6 12H2m0-2h6m-6 4h6M8 6h8M8 18h8m-5 0v4m-2-4v4M8 3v4m0 12v4"
              />
            </svg>
          </span>
          <span>Visual Look</span>
        </a>
        <a
          href="#"
          class="flex items-center p-2 text-gray-700 hover:bg-gray-100 rounded"
        >
          <span class="mr-3">
            <!-- Embed Icon -->
            <svg
              xmlns="http://www.w3.org/2000/svg"
              class="h-5 w-5"
              fill="none"
              viewBox="0 0 24 24"
              stroke="currentColor"
            >
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                d="M8 12h.01M4 7h.01M12 3v4M3 12h18M16 7h.01M12 20v-4m-8 5h16"
              />
            </svg>
          </span>
          <span>Embed on Site</span>
        </a>
        <a
          href="#"
          class="flex items-center p-2 text-gray-700 hover:bg-gray-100 rounded"
        >
          <span class="mr-3">
            <!-- Add-ons Icon -->
            <svg
              xmlns="http://www.w3.org/2000/svg"
              class="h-5 w-5"
              fill="none"
              viewBox="0 0 24 24"
              stroke="currentColor"
            >
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                d="M11 5h-6v7h6V5zm0 7h6V5h-6v7zm-1 6h8M8 17h-3m8-6h1v1m-3 0h1v1m-2-2h1v1m-3 0h1v1m-2-2h1v1m-1 5h5"
              />
            </svg>
          </span>
          <span>Add-ons</span>
        </a>
        <hr class="my-2 border-gray-300" />
        <a
          href="#"
          class="flex items-center p-2 text-gray-700 hover:bg-gray-100 rounded"
        >
          <span class="mr-3">
            <!-- Settings Icon -->
            <svg
              xmlns="http://www.w3.org/2000/svg"
              class="h-5 w-5"
              fill="none"
              viewBox="0 0 24 24"
              stroke="currentColor"
            >
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                d="M12 1v3M8.5 2.5l2 2M1 12h3m16 0h3m-9 7l2 2M6.5 21.5l2-2M21 12l2-2M6 9h12v6H6V9z"
              />
            </svg>
          </span>
          <span>Settings</span>
        </a>
        <a
          href="#"
          class="flex items-center p-2 text-gray-700 hover:bg-gray-100 rounded"
        >
          <span class="mr-3">
            <!-- Integrations Icon -->
            <svg
              xmlns="http://www.w3.org/2000/svg"
              class="h-5 w-5"
              fill="none"
              viewBox="0 0 24 24"
              stroke="currentColor"
            >
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                d="M12 1v22M5 12h14M9 5l6 6-6 6"
              />
            </svg>
          </span>
          <span>Integrations - Soon</span>
        </a>
      </nav>
    </div>

    <!-- Footer Note -->
    <div class="p-4 text-center text-gray-500">
      <p>
        Inspired by
        <a href="https://galichat.com" class="text-blue-500 underline"
          >galichat.com</a
        >
      </p>
    </div>
  </aside>
</template>
