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
  name: "HiddenDeclarationsPage",
  components: {AppPage},
  computed: {
    title() {
      return 'Hidden Declarations';
    },
    description() {
      return 'Sometimes you only want a property declaration to show up some of the time. If a declaration’s value is null or an empty unquoted string, Sass won’t compile that declaration to CSS at all.'
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