<template>
  <div>
    <div class="content-section introduction">
      <div class="feature-intro">
        <h1>{{ title }}</h1>
        <p style="opacity: 0.8">
          {{ description }}
        </p>
      </div>
    </div>
    <br />
    <div class="content-section implementation">
      <div class="content-header">
        <div
          class="demo-tab"
          :class="{ active: demoTab === 'collection' }"
          @click="demoTab = 'collection'"
        >
          Collection
        </div>
        <div
          class="demo-tab"
          :class="{ active: demoTab === 'api' }"
          @click="demoTab = 'api'"
        >
          Properties
        </div>
      </div>
      <div v-show="demoTab === 'collection'">
        <slot></slot>
      </div>
      <div v-show="demoTab === 'api'">
        <slot name="api"></slot>
      </div>
    </div>
  </div>
</template>

<script>
import DocsCardVue from "@/collections/docs-card/DocsCardVue.vue";

export default {
  props: ["title", "description"],
  components: {
    DocsCardVue,
  },
  data() {
    return {
      demoTab: "collection", //'api'
    };
  },
};
</script>

<style lang="scss">
.content-header {
  display: flex;
  width: 100%;
  //   border: 1px solid #cccccc;
  border-radius: 4px;
  overflow: hidden;
  margin: 0 0 2rem 0;
  box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1),
    0 2px 4px -1px rgba(0, 0, 0, 0.06);

  .demo-tab {
    width: 50%;
    text-align: center;
    padding: 0.8rem 0;
    cursor: pointer;

    background-color: #ffffff;
    transition: all 0.2s ease-in-out;
    &:hover {
      background: #edf2f6;
    }
    &.active {
      background-color: #607c8a;
      color: #fff;
    }
  }
}
</style>
