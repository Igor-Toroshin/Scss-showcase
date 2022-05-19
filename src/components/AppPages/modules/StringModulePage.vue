<template>
  <ModulePage :title="title" :code-snippets="codeSnippets">
    <template v-slot:example>
    </template>
  </ModulePage>
</template>

<script>
import ModulePage from "@/components/ModulePage";
export default {
  name: "StringModulePage",
  components: {ModulePage},
  computed: {
    title() {
      return 'Modules: String';
    },
    codeSnippets() {
      return [`string.index("Helvetica Neue", "Helvetica"); // 1
  string.index("Helvetica Neue", "Neue"); // 11
  string.insert("Roboto Bold", " Mono", 7); // "Roboto Mono Bold"
  string.insert("Roboto Bold", " Mono", -6); // "Roboto Mono Bold"
  string.length("Helvetica Neue"); // 14
  string.length(bold); // 4
  string.length(""); // 0
  string.slice("Helvetica Neue", 11); // "Neue"
  string.slice("Helvetica Neue", 1, 3); // "Hel"
  string.slice("Helvetica Neue", 1, -6); // "Helvetica"
   * string.to-upper-case("Bold"); // "BOLD"
  string.to-upper-case(sans-serif); // SANS-SERIF
   * string.to-lower-case("Bold"); // "bold"
  string.to-lower-case(SANS-SERIF); // sans-serif
   * string.unique-id(); // uabtrnzug
  string.unique-id(); // u6w1b1def
  string.unquote("Helvetica"); // Helvetica
  string.unquote(".widget:hover"); // .widget:hover
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