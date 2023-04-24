<template>
  <div class="tab-container" style="">
    <div class="tab-wrapper">
      <h1 class="tab-heading">Run Experiments</h1>
      <div class="search-option">Paper by Andrej Karpathy</div>

      <button class="btn gradient-orange">Add Experiment</button>
      <button class="btn-blur" style="width: 100%; margin-top: 12px">
        Deploy
      </button>
    </div>
    <div class="abt-wrapper">
      <div class="abt-wrapper-header">
        <div class="chip">
          <span style="color: rgb(168 85 247)">Model</span>
          gap-4 (beta)
        </div>
        <button class="btn-blur">Clear all</button>
      </div>
      <div class="abt-wrapper-body"></div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Tab4",
  components: {},
  data() {
    return {
      tab: 0,
    };
  },
};
</script>

<style scoped>
.tab-container {
  width: 100%;
  color: #fff;
  border-radius: 16px;
  margin: 60px 32px 32px 32px;
  background: hsla(0, 0%, 100%, 0.03);
  border: 1px solid hsla(0, 0%, 100%, 0.08);
  display: flex;
  flex-direction: row;
}
.tab-wrapper {
  width: 40%;
  padding: 32px 24px 24px 24px;
  border-right: 1px solid hsla(0, 0%, 100%, 0.08);
  height: 100%;
  backdrop-filter: blur(12px);
  -webkit-backdrop-filter: blur(12px);
}
.tab-heading {
  font-size: 1.5rem;
  line-height: 2rem;
}

.app-search {
  width: 100%;
  border: 1px solid hsla(0, 0%, 100%, 0.08);
  padding: 16px 18px;
  margin-top: 24px;
  border-radius: 8px;
  background: hsla(0, 0%, 100%, 0.03);
  backdrop-filter: blur(12px);
  -webkit-backdrop-filter: blur(12px);
}
.search-option {
  border: 1px solid hsla(0, 0%, 100%, 0.08);
  background: hsla(0, 0%, 100%, 0.03);
  padding: 12px 16px;
  border-radius: 8px;
  margin: 12px 0 0 0;
  color: rgb(203 213 225);
  backdrop-filter: blur(12px);
  -webkit-backdrop-filter: blur(12px);
}
.search-options {
  mask-image: linear-gradient(180deg, #000 0, #000 50%, transparent);
}
.btn {
  width: 100%;
  color: #000;
  font-weight: 700;
  font-size: 16px;
  line-height: 1.75rem;
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: center;
  gap: 10px;
  padding: 8px 20px;
  border-radius: 8px;
  text-align: center;
  margin-top: 32px;
}

.gradient-orange {
  background-image: var(--gradient-orange);
}

.abt-wrapper {
  width: 70%;
  background-color: #000;
}
.abt-wrapper-header {
  width: 100%;
  padding: 12px 16px;
  border-bottom: 1px solid hsla(0, 0%, 100%, 0.08);
  background: hsla(0, 0%, 100%, 0.03);
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: space-between;
}
.chip {
  border-radius: 20px;
  padding: 8px 16px;
  line-height: 1.25rem;
  font-size: 0.875rem;
  background: rgba(255, 255, 255, 0.05);
  border: 1px solid rgba(255, 255, 255, 0.08);
  text-shadow: rgba(0, 0, 0, 0.3) 1px 1px 4px, rgba(0, 0, 0, 0.1) 2px 2px 4px;
  display: flex;
  gap: 18px;
}
.btn-blur {
  padding: 8px 12px;
  font-size: 16px;
  font-weight: 700;
  background: hsla(0, 0%, 100%, 0.03);
  border: 1px solid rgba(255, 255, 255, 0.08);
  border-radius: 8px;
}
</style>
