<template>
  <div class="home-layout">
    <div class="sidebar" v-if="!collapsed">
      <button style="color: #fff" class="sidebar-item" @click="tab = 'home'">
        <svg-icon type="mdi" :path="homePath"></svg-icon>
      </button>

      <ui class="sidebar-container pt-20">
        <button
          class="sidebar-item"
          @click="tab = 0"
          :class="[tab === 0 ? 'gradient-blue' : '']"
        >
          <svg-icon type="mdi" :path="dataPath"></svg-icon
          ><span class="color-grey" :class="[tab === 0 ? 'color-black' : '']"
            >Data Source</span
          >
        </button>
        <button
          class="sidebar-item"
          @click="tab = 1"
          :class="[tab === 1 ? 'gradient-green' : '']"
        >
          <svg-icon type="mdi" :path="promptsPath"></svg-icon>
          <span class="color-grey" :class="[tab === 1 ? 'color-black' : '']"
            >Prompts</span
          >
        </button>
        <button
          class="sidebar-item"
          @click="tab = 2"
          :class="[tab === 2 ? 'gradient-purple' : '']"
        >
          <svg-icon type="mdi" :path="modelPath"></svg-icon>
          <span class="color-grey" :class="[tab === 2 ? 'color-black' : '']"
            >Models</span
          >
        </button>
        <button
          class="sidebar-item"
          @click="tab = 3"
          :class="[tab === 3 ? 'gradient-orange' : '']"
        >
          <svg-icon type="mdi" :path="experimentsPath"></svg-icon>
          <span class="color-grey" :class="[tab === 3 ? 'color-black' : '']"
            >Experiments</span
          >
        </button>
        <button
          class="sidebar-item"
          @click="tab = 4"
          :class="[tab === 4 ? 'gradient-pink' : '']"
        >
          <svg-icon type="mdi" :path="experimentsPath"></svg-icon>
          <span class="color-grey" :class="[tab === 4 ? 'color-black' : '']"
            >Evalutions</span
          >
        </button>
      </ui>
      <div
        class=""
        style="display: flex; flex-direction: row; align-items: center"
      >
        <button class="sidebar-item" @click="tab = 'profile'">
          <svg-icon type="mdi" :path="path"></svg-icon>

          Ramandeep
        </button>
        <button class="sidebar-item">
          <svg-icon
            type="mdi"
            :path="arrowPath"
            @click="collapsed = true"
          ></svg-icon>
        </button>
      </div>
    </div>

    <div v-if="collapsed" class="sidebar sidebar-collapsed">
      <button style="color: #fff" class="sidebar-item" @click="tab = 'home'">
        <svg-icon type="mdi" :path="homePath"></svg-icon>
      </button>

      <ui class="sidebar-container pt-20">
        <button
          class="sidebar-item"
          @click="tab = 0"
          :class="[tab === 0 ? 'gradient-blue' : '']"
        >
          <svg-icon type="mdi" :path="dataPath"></svg-icon>
        </button>
        <button
          class="sidebar-item"
          @click="tab = 1"
          :class="[tab === 1 ? 'gradient-green' : '']"
        >
          <svg-icon type="mdi" :path="promptsPath"></svg-icon>
        </button>
        <button
          class="sidebar-item"
          @click="tab = 2"
          :class="[tab === 2 ? 'gradient-purple' : '']"
        >
          <svg-icon type="mdi" :path="modelPath"></svg-icon>
        </button>
        <button
          class="sidebar-item"
          @click="tab = 3"
          :class="[tab === 3 ? 'gradient-orange' : '']"
        >
          <svg-icon type="mdi" :path="experimentsPath"></svg-icon>
        </button>
        <button
          class="sidebar-item"
          @click="tab = 4"
          :class="[tab === 4 ? 'gradient-pink' : '']"
        >
          <svg-icon type="mdi" :path="experimentsPath"></svg-icon>
        </button>

        <button
          class="sidebar-item"
          @click="tab = 4"
          :class="[tab === 4 ? 'gradient-pink' : '']"
        >
          <svg-icon type="mdi" :path="path"></svg-icon>
        </button>

        <button
          class="sidebar-item"
          @click="collapsed = false"
          :class="[tab === 4 ? 'gradient-pink' : '']"
        >
          <svg-icon type="mdi" :path="arrowPath"></svg-icon>
        </button>
      </ui>
    </div>
    <tab v-if="tab === 0" />
    <tab2 v-if="tab === 1" />
    <tab3 v-if="tab === 2" />
    <tab4 v-if="tab === 3" />
    <tab5 v-if="tab === 4" />
  </div>
</template>

<script>
import SvgIcon from "@jamescoyle/vue-icon";
import {
  mdiAccount,
  mdiLaptop,
  mdiTestTube,
  mdiDatabase,
  mdiHomeVariant,
  mdiChevronRight,
} from "@mdi/js";
import { mdiBookOpenBlankVariant } from "@mdi/js";
import Tab from "@/components/Tabs/ConnectDataSources.vue";
import Tab2 from "@/components/Tabs/ManageTab.vue";
import Tab3 from "@/components/Tabs/Models.vue";
import Tab4 from "@/components/Tabs/RunExperiment.vue";
import Tab5 from "@/components/Tabs/Evalu.vue";

export default {
  name: "Sidebar",
  components: {
    Tab,
    SvgIcon,
    Tab2,
    Tab3,
    Tab4,
    Tab5,
  },
  data() {
    return {
      dataPath: mdiDatabase,
      path: mdiAccount,
      promptsPath: mdiBookOpenBlankVariant,
      modelPath: mdiLaptop,
      experimentsPath: mdiTestTube,
      homePath: mdiHomeVariant,
      arrowPath: mdiChevronRight,

      collapsed: false,
      tab: 0,
    };
  },
};
</script>

<style scoped>
.home-layout {
  display: flex;
  flex-direction: row;
}
.sidebar {
  width: 20%;
  height: 100vh;
  background-color: #000;
  padding: 80px 0 80px 32px;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}
.sidebar-collapsed {
  width: auto;
}

.color-grey {
  color: var(--text-grey);
}
.color-black {
  color: #000;
}
.sidebar-container {
  buttonst-style: none;
  display: flex;
  flex-direction: column;
  gap: 16px;
}
.sidebar-item {
  color: var(--text-grey);
  font-weight: 700;
  font-size: 1.125rem;
  line-height: 1.75rem;
  display: flex;
  flex-direction: row;
  gap: 10px;
  padding: 16px 20px;
  border-radius: 8px;
}
.sidebar-item:hover {
  color: rgba(229, 231, 235, 0.7);
}
.gradient-blue {
  background-image: var(--gradient-blue);
}
.gradient-green {
  background-image: var(--gradient-green);
}
.gradient-purple {
  background-image: var(--gradient-purple);
}
.gradient-orange {
  background-image: var(--gradient-orange);
}
.gradient-pink {
  background-image: var(--gradient-pink);
}
</style>
