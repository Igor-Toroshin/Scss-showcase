<template>
  <ModulePage :title="title" :code-snippet="codeSnippet">
    <template v-slot:example>
      <div class="example-container">
        <div class="start-btn">
          <button class="button">button</button>
          <button class="button">button</button>
          <button class="button">button</button>
          <button class="button">button</button>
          <button class="button">button</button>
          <button class="button">button</button>
          <button class="button">button</button>
          <button class="button">button</button>
          <button class="button">button</button>
          <button class="button">button</button></div>
        <div class="text-container">
          <span class="text">background-color: adjust-hue($color, 60deg);</span>
          <span class="text">background-color: complement($color);</span>
          <span class="text">background-color: lighten($color, 25%);</span>
          <span class="text">background-color: darken($color, 25%);</span>
          <span class="text">background-color: desaturate($color, 50%);</span>
          <span class="text">background-color: grayscale($color);</span>
          <span class="text">background-color: invert($color);</span>
          <span class="text">background-color: fade-in($color,0.25%);</span>
          <span class="text">background-color: transparentize($color,0.25%);</span>
          <span class="text">background-color: fade-out($color,0.25%);</span>
        </div>
        <div class="end-btn">
          <button class="button button-hue">button</button>
          <button class="button button-complement">button</button>
          <button class="button button-lighten">button</button>
          <button class="button button-darken">button</button>
          <button class="button button-desaturate">button</button>
          <button class="button button-grayscale">button</button>
          <button class="button button-invert">button</button>
          <button class="button button-fade-in">button</button>
          <button class="button button-transparentize">button</button>
          <button class="button button-fade-out">button</button>
        </div>
      </div>
    </template>
  </ModulePage>
</template>

<script>
import ModulePage from "@/components/ModulePage";
export default {
  name: "ColorModulePage",
  components: {ModulePage},
  computed: {
    title() {
      return 'Modules: Color';
    },
    codeSnippet() {
      return `adjust($color, $red: null, $green: null,
  $blue: null, $hue: null, $saturation: null, $lightness: null,
  $whiteness: null, $blackness: null, $alpha: null)
  adjust-hue($color, $degrees)
  red($color) - for getting a color’s red channel.
  green($color) - for getting a color’s green channel.
  blue($color) - for getting a color’s blue channel.
  hue($color) - for getting a color’s hue.
  saturation($color) - for getting a color’s saturation.
  lightness($color) - for getting a color’s lightness.
  blackness($color) - Returns the blackness of $color.
  whiteness($color) - Returns the whiteness of $color.
  alpha() - for getting a color’s alpha - channel.
   * complement($color) - Returns the RGB complement of $color.
   * lighten($color, $amount) - Makes - $color - lighter.
   * darken($color, $amount) - Makes $color darker
  desaturate($color, $amount) - Makes $color less saturated.
   * grayscale($color) - Returns a gray color with the same lightness.
  invert($color, $weight: 100%) - Returns the inverse of $color.
  mix($color1, $color2, $weight: 50%) - Returns a color that’s a mixture
  fade-in($color, $amount) - Makes $color more opaque.
  transparentize($color, $amount) Makes $color more transparent.
  fade-out($color, $amount) - Makes $color more transparent.
  `
    }
  }
}
</script>

<style scoped lang="scss">
$color: #4bdef8;

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