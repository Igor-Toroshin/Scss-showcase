<template>
  <AppPage :title="title" :description="description" :code-snippets="codeSnippets">
    <template v-slot:example>
      <div class="circle-container">
        <button class="default-button">button</button>
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
  name: "MixinPage",
  components: {AppPage},
  computed: {
    title() {
      return 'At-Rules: Mixin and Include';
    },
    description() {
      return `Mixins allow you to define styles that can be re-used throughout your stylesheet.`;
    },
    codeSnippets() {
      return [`@mixin center-element {
    display: flex;
    justify-content: center;
    align-items: center;
  }
  $color: #4bdef8;
  @mixin button($color: $color) {
    color: white;
    background: $color;
    border-radius: 10px;
    box-shadow: $color 0 10px 20px -10px;
    margin: 5px;
    font-size: 16px;
    font-weight: 700;
    line-height: 24px;
    padding: 8px 18px;
    width: fit-content;
    border: 0;
  }}`,`.default-button {
    @include button();
  }

  .warning-button {
    @include button(#f0c65d);
  }

  .error-button {
    @include button(#f05d5d);
  }

  .confirm-button {
    @include button(#71f05d);
  }`]
    }
  }
}
</script>

<style scoped lang="scss">
@mixin center-element {
  display: flex;
  justify-content: center;
  align-items: center;
}
$color: #4bdef8;
@mixin button($color: $color) {
  color: white;
  background: $color;
  border-radius: 10px;
  box-shadow: $color 0 10px 20px -10px;
  margin: 5px;
  font-size: 16px;
  font-weight: 700;
  line-height: 24px;
  padding: 8px 18px;
  width: fit-content;
  border: 0;
}
.default-button {
  @include button()
}

.warning-button {
  @include button(#f0c65d);
}

.error-button {
  @include button(#f05d5d);
}

.confirm-button {
  @include button(#71f05d);
}
</style>