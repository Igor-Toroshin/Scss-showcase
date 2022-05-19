<template>
  <AppPage :title="title" :description="description" :code-snippets="codeSnippets">
    <template v-slot:example>
<!--      <button class="default margin-size-2">button</button>-->
<!--      <button class="confirm margin-size-3">confirm-button</button>-->
<!--      <button class="warning margin-size-5">warning-button</button>-->
<!--      <button class="error margin-size-7">error-button</button>-->
      <div id="container" class="container">
        <div v-for="index in 100" :key="index" class="item"></div>
      </div>
    </template>
  </AppPage>
</template>

<script>
import AppPage from "@/components/AppPage";
export default {
  name: "ForPage",
  components: {AppPage},
  computed: {
    title() {
      return 'At-Rules Flow-Control: For';
    },
    description() {
      return 'The @for rule counts up or down from one number (the result of the first expression) to another (the result of the second) and evaluates a block for each number in between. Each number along the way is assigned to the given variable name. If to is used, the final number is excluded; if through is used, it\'s included.'
    },
    codeSnippets() {
      return [`$base-color: #036;
  @for $i from 1 through 100 {
    .item:nth-child(#{$i}) {
      background-color: lighten($base-color, $i * 1%);
    }
  }`,`Design System - Variables.scss

  @for $i from 0 through 20 {
    --size-value#{$i}: #{$i * 4}px;
  }`]
    }
  }
}
</script>

<style scoped lang="scss">
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
    warning: #f0c65d,
    confirm: #71f05d,
    error: #f05d5d
);


@each $name, $value in $buttons {
  .#{$name} {
    @include button($value);
  }
}

$base-color: #036;
@for $i from 1 through 100 {
  .item:nth-child(#{$i}) {
    background-color: lighten($base-color, $i * 1%);
    //transition: height 1s ease-in-out;
    //&:hover {
    //  height: 45%;
    //  transition: border-radius .55s ease-in-out;
    //}
  }
}

@for $i from 1 through 8 {
  .font-size-#{$i} {
    font-size: $i * 4px !important;
  }
}

.container{
  align-items: center;
  display: flex;
  height: 100%;
  width: 80%;
  flex: 1;
}

.item {
  height: 30%;
  flex: 1;
}
</style>