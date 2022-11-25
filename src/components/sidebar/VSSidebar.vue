<template>
  <div class="sidebar" :style="{ width: sidebarWidth }">
    <h1>
      <span v-if="collapsed">
        <div>H</div>
        <div>C</div>
      </span>
      <span v-else>Chava Sidebar</span>
    </h1>
    <SidebarLink goTo="/" icon="fas fa-home">Home</SidebarLink>
    <SidebarLink goTo="/dashboard" icon="fas fa-columns">Dashboard</SidebarLink>
    <SidebarLink goTo="/analytics" icon="fas fa-chart-var"
      >Analytics</SidebarLink
    >
    <SidebarLink goTo="/friends" icon="fas fa-users">Friends</SidebarLink>
    <SidebarLink goTo="/image" icon="fas fa-image">Images</SidebarLink>
    <span
      :class="{ 'rotate-180': collapsed }"
      class="collapse-icon"
      @click="toggleSidebar"
    >
      <i class="fas fa-angle-double-left"></i>
    </span>
  </div>
</template>

<script>
import { collapsed, toggleSidebar, sidebarWidth } from "./state";
import SidebarLink from "./SidebarLink.vue";
export default {
  props: {},
  components: {
    SidebarLink,
  },
  setup() {
    return {
      collapsed,
      toggleSidebar,
      sidebarWidth,
    };
  },
};
</script>

<style>
/* GLOBAL STYLES */
:root {
  --sidebar-bg-color: #2f855a;
  --sidebar-item-hover: #38a169;
  --sidebar-item-active: #276749;
}
</style>

<style scoped>
.sidebar {
  color: white;
  background-color: var(--sidebar-bg-color);
  float: left;
  position: fixed;
  z-index: 1;
  top: 0;
  left: 0;
  bottom: 0;
  padding: 0.5em;

  transition: 0.3s ease;

  display: flex;
  flex-direction: column;
}

.collapse-icon {
  position: absolute;
  bottom: 0;
  padding: 0.75em;
  color: rgba(255, 255, 255, 0.7);
  transition: 0.2s linear;
}

.rotate-180 {
  transform: rotate(180deg);
  transition: 0.2s linear;
}
</style>
