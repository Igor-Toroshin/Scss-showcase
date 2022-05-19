<template>
  <AppPage :title="title" :description="description" :code-snippets="codeSnippets">
    <template v-slot:example>
      <div class="button">
        <span class="text">Click me!</span>
      </div>
    </template>
  </AppPage>
</template>

<script>
import AppPage from "@/components/AppPage";
export default {
  name: "WhilePage",
  components: {AppPage},
  computed: {
    title() {
      return 'At-Rules Flow-Control: While';
    },
    description() {
      return 'The @for rule counts up or down from one number (the result of the first expression) to another (the result of the second) and evaluates a block for each number in between. Each number along the way is assigned to the given variable name. If to is used, the final number is excluded; if through is used, it\'s included.'
    },
    codeSnippets() {
      return [`// SCSS.
  $base-color: #036;

  @for $i from 1 through 3 {
    ul:nth-child(3n + #{$i}) {
      background-color: lighten($base-color, $i * 5%);
    }
  }`,`// CSS.
  ul:nth-child(3n + 1) {
    background-color: #004080;
  }

  ul:nth-child(3n + 2) {
    background-color: #004d99;
  }

  ul:nth-child(3n + 3) {
    background-color: #0059b3;
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