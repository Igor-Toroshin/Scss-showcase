<template>
  <AppPage :title="title" :description="description" :code-snippets="codeSnippets">
    <template v-slot:example>
      <button class="button-1">button</button>
      <button class="button-2">button</button>
      <button class="button-3">button</button>
    </template>
  </AppPage>
</template>

<script>
import AppPage from "@/components/AppPage";
export default {
  name: "FunctionPage",
  components: {AppPage},
  computed: {
    title() {
      return 'At-Rules: Function';
    },
    description() {
      return `Functions allow you to define complex operations on SassScript values that you can re-use throughout your stylesheet. They make it easy to abstract out common formulas and behaviors in a readable way.`
    },
    codeSnippets() {
      return [`@function randomNum($min: 0, $max: 100) {
    $rand: random();
    $randomNum: $min + floor($rand * (($max - $min) + 1));

    @return $randomNum;
  }
  @function sum($numbers...) {
    $sum: 0;
    @each $number in $numbers {
      $sum: $sum + $number;
    }
    @return $sum;
  }`,`.button {
    width: sum(50px, 30px, 100px);

    padding-left: randomNum(1px,60px);
    padding-right: randomNum(1px,60px);
    padding-top: randomNum(1px,60px);
    padding-bottom: randomNum(1px,60px);
  }`]
    }
  }
}
</script>

<style scoped lang="scss">
@function randomNum($min: 0, $max: 100) {
  $rand: random();
  $randomNum: $min + floor($rand * (($max - $min) + 1));

  @return $randomNum;
}


.button {
  background: #4bdef8;
  border-radius: 10px;
  box-shadow: #4bdef8 0 10px 20px -10px;
  color: #FFFFFF;
  font-size: 16px;
  font-weight: 700;
  margin: 10px;
  line-height: 24px;
  border: 0;
}

@function sum($numbers...) {
  $sum: 0;
  @each $number in $numbers {
    $sum: $sum + $number;
  }
  @return $sum;
}

.button-1 {
  @extend .button;
  width: sum(50px, 30px, 100px);
  padding-left: randomNum(1px,60px);
  padding-right: randomNum(1px,60px);
  padding-top: randomNum(1px,60px);
  padding-bottom: randomNum(1px,60px);
}
.button-2 {
  @extend .button;
  width: sum(50px, 30px, 100px);
  padding-left: randomNum(1px,60px);
  padding-right: randomNum(1px,60px);
  padding-top: randomNum(1px,60px);
  padding-bottom: randomNum(1px,60px);
}
.button-3 {
  @extend .button;
  width: sum(50px, 30px, 100px);
  padding-left: randomNum(1px,60px);
  padding-right: randomNum(1px,60px);
  padding-top: randomNum(1px,60px);
  padding-bottom: randomNum(1px,60px);
}

</style>