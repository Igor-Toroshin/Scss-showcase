<template>
  <AppPage :title="title" :description="description" :code-snippets="codeSnippets">
    <template v-slot:example>
      <div class="container">
        <div >
          <button class="button">button</button>
          <button class="confirm-button">confirm-button</button>
          <button class="warning-button">warning-button</button>
          <button class="error-button">error-button</button>

        </div>
        <div>

          <button class="dark-button">button</button>
          <button class="dark-confirm-button">confirm-button</button>
          <button class="dark-warning-button">warning-button</button>
          <button class="dark-error-button">error-button</button>
        </div>
      </div>

    </template>
  </AppPage>
</template>

<script>
import AppPage from "@/components/AppPage";
export default {
  name: "IfAndElsePage",
  components: {AppPage},
  computed: {
    title() {
      return 'At-Rules Flow-Control: If, Else';
    },
    description() {
      return 'The @if controls whether or not its block gets evaluated. If the expression returns true, the block is evaluated, and if the expression returns false it’s not.'
    },
    codeSnippets() {
      return [`$dark-background: #6b717f;

  @mixin theme-colors($light, $color) {
    @if $light {
      background-color: $color;
      color: #fff;
    } @else {
      background-color: $dark-background;
      color: $color;
    }
  }`,`$light-theme: false;

  .dark-button {
    @include button($default, $light-theme);
  }
  .dark-warning-button {
    @include button($warning, $light-theme);
  }
  .dark-error-button {
    @include button($error, $light-theme);
  }
  .dark-confirm-button {
    @include button($confirm, $light-theme);
  }`
        ,`@mixin button($color, $theme) {
    @include theme-colors($theme, $color);
    margin: 5px;
    border-radius: 10px;
    box-shadow: $color 0 10px 20px -10px;
    font-size: 16px;
    font-weight: 700;
    line-height: 24px;
    padding: 8px 18px;
    width: fit-content;
    border: 0;
  }`]
    }
  }
}
</script>

<style scoped lang="scss">
.container {
  display: flex;
  flex-direction: column;
}
$dark-background: #6b717f;
$dark-theme: false;
$light-theme: true;
$warning-color: #f0c65d;
$error-color: #f05d5d;
$confirm-color: #71f05d;
$default-color: #5ddaf0;

@mixin theme-colors($light-theme, $color) {
  @if $light-theme {
    background-color: $color;
    color: #fff;
  } @else {
    background-color: mix($dark-background, $color, 80%);
    color: $color;
  }
}
@mixin button($color, $light-theme) {
  @include theme-colors($light-theme, $color);
  margin: 5px;
  border-radius: 10px;
  box-shadow: $color 0 10px 20px -10px;
  font-size: 16px;
  font-weight: 700;
  line-height: 24px;
  padding: 8px 18px;
  width: fit-content;
  border: 0;
}

.button {
  @include button($default-color, $light-theme);
}

.warning-button {
  @include button($warning-color, $light-theme);
}

.error-button {
  @include button($error-color, $light-theme);
}

.confirm-button {
  @include button($confirm-color, $light-theme);
}

.dark-button {
  @include button($default-color, $dark-theme);
}
.dark-warning-button {
  @include button($warning-color, $dark-theme);
}
.dark-error-button {
  @include button($error-color, $dark-theme);
}
.dark-confirm-button {
  @include button($confirm-color, $dark-theme);
}
</style>