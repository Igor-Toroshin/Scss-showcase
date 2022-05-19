<template>
  <AppPage :title="title" :description="description" :code-snippets="codeSnippets">
    <template v-slot:example>
    </template>
  </AppPage>
</template>

<script>
import AppPage from "@/components/AppPage";
export default {
  name: "UsePage",
  components: {AppPage},
  computed: {
    title() {
      return 'At-Rules: Use';
    },
    description() {
      return `The @use rule loads mixins, functions, and variables from other Sass stylesheets, and combines CSS from multiple stylesheets together. `
    },
    codeSnippets() {
      return [`// src/_corners.scss
  $radius: 3px;

  @mixin rounded {
    border-radius: $radius;
  }


  // style.scss
  @use "src/corners" as c;

  .button {
    @include c.rounded;
    padding: 5px + corners.$radius;
  }`,`// CSS.
  .button {
    border-radius: 3px;
    padding: 8px;
  }`]
    }
  }
}
</script>

<style scoped lang="scss">
$base-color: #c6538c;
$border-dark: rgba($base-color, 0.88);

.button {
  border: 1px solid $border-dark;
  .text {
    font-size: 1.5em;
  }
}
</style>