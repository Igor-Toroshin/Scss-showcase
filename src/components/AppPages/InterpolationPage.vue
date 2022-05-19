<template>
  <AppPage :title="title" :description="description" :code-snippets="codeSnippets">
    <template v-slot:example>
      <div class="container">
        <button class="button">button</button>
        <button class="confirm-button">confirm-button</button>
        <button class="warning-button">warning-button</button>
        <button class="error-button">error-button</button>
      </div>
    </template>
  </AppPage>
</template>

<script>
import AppPage from "@/components/AppPage";
export default {
  name: "InterpolationPage",
  components: {AppPage},
  computed: {
    title() {
      return 'Interpolation';
    },
    description() {
      return `Interpolation can be used almost anywhere in a Sass stylesheet to embed the result of a SassScript expression into a chunk of CSS. Just wrap an expression in #{}`},
    codeSnippets() {
      return [`@mixin corner-element($top-or-bottom, $left-or-right) {
    position: absolute;
    #{$top-or-bottom}: 20%;
    #{$left-or-right}: 20%;
  }`, `.button {
    @include corner-element(bottom, right);
  }
  .warning-button {
    @include corner-element(top, left);
  }
  .confirm-button {
    @include corner-element(bottom, left);
  }
  .error-button {
    @include corner-element(top, right);
  }`]
    }
  }
}
</script>

<style scoped lang="scss">
@mixin corner-element($top-or-bottom, $left-or-right) {
  position: absolute;
  #{$top-or-bottom}: 20%;
  #{$left-or-right}: 20%;
}

.container {
  position: relative;
  display: flex;
  flex: 1;
  height: 100%
}
.button {
  background: #4bdef8;
  border-radius: 10px;
  box-shadow: #4bdef8 0 10px 20px -10px;
  color: #FFFFFF;
  font-size: 16px;
  font-weight: 700;
  line-height: 24px;
  padding: 8px 18px;
  width: fit-content;
  height: fit-content;
  border: 0;
}

.warning-button {
  @extend .button;
  @include corner-element(top, left);
  background: #f0c65d;
  box-shadow: #f0c65d 0 10px 20px -10px;
}

.error-button {
  @extend .button;
  background: #f05d5d;
  box-shadow: #f05d5d 0 10px 20px -10px;
}

.confirm-button {
  @extend .button;
  background: #71f05d;
  box-shadow: #71f05d 0 10px 20px -10px;
}


.button {
  @include corner-element(bottom, right);
}
.warning-button {
  @include corner-element(top, left);
}
.confirm-button {
  @include corner-element(bottom, left);
}
.error-button {
  @include corner-element(top, right);
}
</style>