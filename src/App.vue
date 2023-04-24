<template>
  <div>
    <div className="absolute">
      <div className="faint-glow-blue"></div>
      <div className="faint-glow-red"></div>
    </div>
    <div className="absolute-right">
      <div className="faint-glow-blue"></div>
      <div className="faint-glow-red"></div>
    </div>
    <Sidebar />
  </div>
</template>

<script>
import Sidebar from "./components/sidebar/Sidebar.vue";

export default {
  name: "App",
  components: {
    Sidebar,
  },
};
</script>

<style></style>
