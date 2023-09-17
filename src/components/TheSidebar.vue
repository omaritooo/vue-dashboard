<template>
  <aside
    class="fixed top-0 left-0 z-40 flex flex-col justify-between w-1/6 h-screen px-6 py-8 bg-white shadow-lg rounded-r-md"
  >
    <h1 class="flex items-center justify-start text-black gap-x-2">
      <IconLogo />
      <span class="text-xl"> Dashboard </span>
    </h1>
    <ul class="flex flex-col w-full mt-6 h-fit gap-y-3">
      <BaseSideMenuItem v-for="route in routes" :key="route.name" :route="route" />
    </ul>
    <div
      class="relative z-40 flex flex-col items-center w-full p-4 mt-auto rounded-lg bg-primary"
    >
      <div class="flex flex-col items-center">
        <IconLogo />
        <span class="text-base font-bold text-white"> Dashboard Pro </span>
        <p class="w-3/4 text-sm text-center text-gray-300">
          Get access to all features on tetumbas
        </p>
        <button
          class="w-3/4 py-1 mt-4 text-base font-bold bg-white rounded-sm text-primary"
        >
          Get Pro
        </button>
      </div>
    </div>
  </aside>
</template>
<script setup lang="ts">
import IconLogo from "./Icon/IconLogo.vue";
import BaseSideMenuItem from "./Base/BaseSideMenuItem.vue";
import { reactive } from "vue";
import type { Route } from "@/types";
const routes: Route[] = reactive([
  {
    name: "Dashboard",
    route: "/",
  },
  {
    name: "Leaderboard",
    route: "/leaderboard",
  },
  {
    name: "Order",
    route: "/order",
  },
  {
    name: "Products",
    route: "/products",
  },
  {
    name: "Messages",
    route: "/messages",
  },
  {
    name: "Settings",
    route: "/settings",
  },
]);
</script>
