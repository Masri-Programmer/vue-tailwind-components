<script setup lang="ts">
defineProps<{ direction: "left" | "right" }>();
import { ref } from "vue";
import Sidebar from "@components/Sidebar.vue";
const toggler = ref(false);
const handleNavToggle = (): void => {
  toggler.value = !toggler.value;
};
</script>

<template>
  <Sidebar
    @handleclickOutside="handleNavToggle"
    :toggler="toggler"
    :direction="direction"
    class="block lg:hidden"
  />
  <nav
    class="relative flex flex-wrap items-center justify-between px-2 py-3 mb-3 shadow-md"
  >
    <div
      class="container mx-auto flex flex-wrap items-center justify-between"
      :class="direction === 'right' && ' flex-row-reverse'"
    >
      <div
        class="w-full relative flex justify-between lg:w-auto px-4 lg:static lg:block lg:justify-start"
        :class="direction === 'right' && ' flex-row-reverse'"
      >
        <a
          class="text-sm font-bold leading-relaxed inline-block mr-4 py-2 whitespace-nowrap uppercase text-black"
          href="#pablo"
        >
          Slate Color
        </a>
        <button
          class="cursor-pointer text-xl leading-none px-4 py-1 border border-solid border-transparent rounded bg-transparent block lg:hidden outline-none focus:outline-none"
          @click="handleNavToggle"
          type="button"
        >
          <span class="block relative w-6 h-px rounded-sm bg-black"></span>
          <span class="block relative w-6 h-px rounded-sm bg-black mt-1"></span>
          <span class="block relative w-6 h-px rounded-sm bg-black mt-1"></span>
        </button>
      </div>
      <div class="lg:flex flex-grow items-center" id="example-navbar-warning">
        <ul
          class="hidden lg:flex list-none"
          :class="direction === 'right' ? '' : 'ml-auto'"
        >
          <li class="nav-item">
            <a
              class="px-3 py-2 flex items-center text-xs uppercase font-bold leading-snug text-black hover:opacity-75"
              href="#pablo"
            >
              Discover
            </a>
          </li>
          <li class="nav-item">
            <a
              class="px-3 py-2 flex items-center text-xs uppercase font-bold leading-snug text-black hover:opacity-75"
              href="#pablo"
            >
              Profile
            </a>
          </li>
          <li class="nav-item">
            <a
              class="px-3 py-2 flex items-center text-xs uppercase font-bold leading-snug text-black hover:opacity-75"
              href="#pablo"
            >
              Setting
            </a>
          </li>
        </ul>
      </div>
    </div>
  </nav>
</template>

<style scoped>
.read-the-docs {
  color: #888;
}
</style>
