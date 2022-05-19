<template>
  <AppPage :title="title" :description="description" :code-snippets="codeSnippets">
    <template v-slot:example>
      <button class="button">button</button>
      <button class="confirm-button">confirm-button</button>
      <button class="warning-button">warning-button</button>
      <button class="error-button">error-button</button>
    </template>
  </AppPage>
</template>

<script>
import AppPage from "@/components/AppPage";
export default {
  name: "ExtendPage",
  components: {AppPage},
  computed: {
    title() {
      return 'At-Rules: Extend';
    },
    description() {
      return 'There are often cases when designing a page when one class should have all the styles of another class, as well as its own specific styles. ';
    },
    codeSnippets() {
      return [`.button {
    background: #4bdef8;
    border-radius: 10px;
    box-shadow: #4bdef8 0 10px 20px -10px;
    color: #FFFFFF;
    font-size: 16px;
    font-weight: 700;
    line-height: 24px;
    padding: 8px 18px;
    width: fit-content;
    border: 0;
  }`,`.warning-button {
    @extend .button;
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
  }`]
    }
  }
}
</script>

<style scoped lang="scss">

.button {
  background: #4bdef8;
  border-radius: 10px;
  box-shadow: #4bdef8 0 10px 20px -10px;
  color: #FFFFFF;
  font-size: 16px;
  font-weight: 700;
  line-height: 24px;
  margin: 5px;
  padding: 8px 18px;
  width: fit-content;
  border: 0;
}

.warning-button {
  @extend .button;
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
</style>