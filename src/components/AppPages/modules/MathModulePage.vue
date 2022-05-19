<template>
  <ModulePage :title="title" :code-snippets="codeSnippets">
    <template v-slot:example>
    </template>
  </ModulePage>
</template>

<script>
import ModulePage from "@/components/ModulePage";
export default {
  name: "MathModulePage",
  components: {ModulePage},
  computed: {
    title() {
      return 'Modules: Math';
    },
    codeSnippets() {
      return [`ceil(4); // 4
   * ceil(4.2); // 5
  clamp(-1, 0, 1); // 0
  clamp(1px, -1px, 10px); // 1px
  clamp(-1in, 1cm, 10mm); // 10mm
  floor(4); // 4
  floor(4.2); // 4
  floor(4.9); // 4
   * max(1px, 4px); // 4px

  $widths: 50px, 30px, 100px;
  max($widths...); // 100px
   * min(1px, 4px); // 1px
  $widths: 50px, 30px, 100px;
  min($widths...); // 30px
`,`percentage(0.2); // 20%
  percentage(div(100px, 50px)); // 200%
   * random(); // 0.2821251858
  random(); // 0.6221325814
  random(10); // 4
  random(10000); // 5373.
  round(4); // 4
  round(4.2); // 4
  round(4.9); // 5

  abs(10px); // 10px
   * abs(-10px); // 10px
  log(10); // 2.302585093
  log(10, 10); // 1
  unit(100); // ""
  unit(100px); // "px"
  unit(5px * 10px); // "px*px"
  unit(div(5px, 1s)); // "px/s"
  div($number1, $number2) //=> number
  `,`pow(10, 2); // 100
  pow(100, div(1, 3)); // 4.6415888336
  pow(5, -2); // 0.04
  sqrt(100); // 10
  sqrt(div(1, 3)); // 0.5773502692
  sqrt(-1); // NaN
  cos(1); // 0.5403023059
  sin(1); // 0.8414709848
  tan(1); // 1.5574077247
  compatible(2px, 1px); // true
  compatible(100px, 3em); // false
  compatible(10cm, 3mm); // true
  is-unitless(100); // true
  is-unitless(100px); // false
  `]
    }
  }
}
</script>

<style scoped lang="scss">
$color: #5E5DF0;
.button {
  background: $color;
  border-radius: 10px;
  box-shadow: $color 0 10px 20px -10px;
  color: #FFFFFF;
  font-size: 16px;
  font-weight: 700;
  line-height: 24px;
  padding: 8px 16px;
  margin: 5px;
  width: fit-content;
  height: fit-content;
  border: 0;
}
.example-container {
  display: flex;
  flex: 1;
  flex-direction: row;
  align-items: center;
}
.start-btn {
  display: flex;
  flex:1;
  flex-direction: column;
  align-items: flex-end;
}
.text-container {
  display: flex;
  flex:3;
  flex-direction: column;
  .text {
    color: #000;
    font-size: 16px;
    font-weight: 700;
    line-height: 24px;
    padding: 8px 16px;
    margin: 5px;
  }
}
.end-btn {
  display: flex;
  flex: 1;
  flex-direction: column;
  align-items: flex-start;
}

.button-hue {
  background-color: adjust-hue($color, 60deg);
}
.button-complement {
  background-color: complement($color);
}
.button-lighten {
  background-color: lighten($color, 25%);
}
.button-darken {
  background-color: darken($color, 25%);
}
.button-desaturate {
  background-color: desaturate($color, 50%);
}
.button-grayscale {
  background-color: grayscale($color);
}
.button-invert {
  background-color: invert($color);
}
.button-fade-in {
  background-color: fade-in($color, 0.25%);
}
.button-fade-out {
  background-color: fade-out($color, 0.25%);
}
.button-transparentize {
  background-color: transparentize($color, 0.25%);
}
</style>