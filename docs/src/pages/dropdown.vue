<template>
  <docs-page :title="$options.title" :description="$options.description">
    <template #api>
      <docs-properties api-path="/api/buttons.json" />
    </template>
    <docs-card-vue title="Dropdown" file="examples/dropdown/Dropdown" />
  </docs-page>
</template>

<script>
import DocsPage from "@/layouts/docs-page.vue";
import DocsProperties from "@/collections/DocsProperties.vue";
import DocsCardVue from "@/collections/docs-card/DocsCardVue.vue";

export default {
  components: {
    DocsCardVue,
    DocsProperties,
    DocsPage,
  },
  title: "Dropdown",
  description: `These buttons colection of Flex UI gives user the option to use any button according to the need of the project`,
};
</script>
