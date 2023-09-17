<template>
  <RouterLink :to="route.route">
    <component :is="componentIcon[route.name as keyof typeof componentIcon]" />
    <span class="w-full">{{ route.name }}</span>
  </RouterLink>
</template>
<script setup lang="ts">
import type { Route } from "@/types";
import { defineAsyncComponent } from "vue";
import { RouterLink } from "vue-router";

const IconDashboard = defineAsyncComponent(() => import("../Icon/IconDashboard.vue"));
const IconLeaderboard = defineAsyncComponent(() => import("../Icon/IconLeaderboard.vue"));
const IconProduct = defineAsyncComponent(() => import("../Icon/IconProduct.vue"));
const IconOrder = defineAsyncComponent(() => import("../Icon/IconOrder.vue"));
const IconMessages = defineAsyncComponent(() => import("../Icon/IconMessages.vue"));
const IconSettings = defineAsyncComponent(() => import("../Icon/IconSettings.vue"));
defineProps<{
  route: Route;
}>();

const componentIcon = {
  Dashboard: IconDashboard,
  Leaderboard: IconLeaderboard,
  Products: IconProduct,
  Order: IconOrder,
  Messages: IconMessages,
  Settings: IconSettings,
};
</script>
<style scoped>
a {
  color: black;
  width: 100%;
  min-width: 150px;
  gap: 10px;
  padding: 0 10px;
  height: 45px;
  border-radius: 10px;
  display: flex;
  justify-content: flex-start;
  align-items: center;
}
a:hover {
  background-color: #5d5fef;
  color: white;
}

a.router-link-exact-active {
  background-color: #5d5fef;
  color: white;
}
/* a.router-link-active {
  background-color: red;
} */
</style>
