<template>
  <AppPage :title="title" :description="description" :code-snippets="codeSnippets">
    <template v-slot:example>
      <div>
        <button class="default"></button>
        <button class="default-2"></button>
        <button class="default-3"></button>
        <button class="default-4"></button>

        <button class="confirm"></button>
        <button class="confirm-2"></button>
        <button class="confirm-3"></button>
        <button class="confirm-4"></button>

        <button class="warning"></button>
        <button class="warning-2"></button>
        <button class="warning-3"></button>
        <button class="warning-4"></button>

        <button class="error"></button>
        <button class="error-2"></button>
        <button class="error-3"></button>
        <button class="error-4"></button>

        <button class="default"></button>
        <button class="default-2"></button>
        <button class="default-3"></button>
        <button class="default-4"></button>

        <button class="confirm"></button>
        <button class="confirm-2"></button>
        <button class="confirm-3"></button>
        <button class="confirm-4"></button>

        <button class="warning"></button>
        <button class="warning-2"></button>
        <button class="warning-3"></button>
        <button class="warning-4"></button>

        <button class="error"></button>
        <button class="error-2"></button>
        <button class="error-3"></button>
        <button class="error-4"></button>
      </div>
    </template>
  </AppPage>
</template>

<script>
import AppPage from "@/components/AppPage";
export default {
  name: "EachPage",
  components: {AppPage},
  computed: {
    title() {
      return 'At-Rules Flow-Control: Each, and Map';
    },
    description() {
      return 'The @each rule makes it easy to emit styles or evaluate code for each element of a list or each pair in a map. It’s great for repetitive styles that only have a few variations between them. '
    },
    codeSnippets() {
      return [`$buttons: (
      default: #5ddaf0,
      default-2: #5dcef0,
      default-3: #5db8f0,
      default-4: #5d9df0,
      warning: #f0c65d,
      warning-2: #f0dc5d,
      warning-3: #f0e95d,
      warning-4: #e1f05d,
      confirm: #71f05d,
      confirm-2: #67f05d,
      ...
  );`,`@each $name, $value in $buttons {
    .#{$name} {
      @include button($value);
      &::after {
        content: '#{$name}';
      }
    }
  }`,`@mixin button($color) {
    background-color: $color;
    color: #fff;
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

<style lang="scss">
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
    background-color: $dark-background;
    color: $color;
  }
}
@mixin button($color) {
  background-color: $color;
  color: #fff;
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

$buttons: (
    default: #5ddaf0,
    default-2: #5dcef0,
    default-3: #5db8f0,
    default-4: #5d9df0,
    warning: #f0c65d,
    warning-2: #f0dc5d,
    warning-3: #f0e95d,
    warning-4: #e1f05d,
    confirm: #71f05d,
    confirm-2: #67f05d,
    confirm-3: #5df064,
    confirm-4: #5df075,
    error: #f05d5d,
    error-2: #f06e5d,
    error-3: #f07f5d,
    error-4: #f0845d,
);
@each $name, $value in $buttons {
  .#{$name} {
    @include button($value);
    &::after {
      content: '#{$name}';
    }
  }
}


</style>