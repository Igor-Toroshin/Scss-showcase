<template>
  <div class="app-page">
    <div class="__title">{{ title }}</div>
    <div v-if="description" class="__description">{{ description }}</div>
    <div class="__code-snippet">
      <CodeSnippet v-for="(codeSnippet, index) in codeSnippets"
                   :key="index"
                   :code="codeSnippet"/>
    </div>
    <div class="__example">
      <slot name="example">__example</slot>
    </div>
  </div>
</template>

<script>
import CodeSnippet from "@/components/CodeSnippet";
export default {
  name: 'AppPage',
  components: {CodeSnippet},
  props: {
    title : {
      type: String
    },
    description : {
      type: String
    },
    codeSnippets : {
      type: Array,
      default: () => []
    }
  },
  computed: {
    test() {
      return '';
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.app-page {
  display: flex;
  flex: 1;
  flex-direction: column;
  $backgroundColor: #f8f8f8;
  $secondary: #4bdef8;
  $color:black;
  background-color: $backgroundColor;
  color: $color;

  .__title {
    display: flex;
    align-items: center;
    justify-content: center;

    height: 10vh;
    background-color: $secondary;
    color: white;
    //text-shadow: -1px 0 black, 0 1px black, 1px 0 black, 0 -1px black;
    text-shadow: 1px 4px 3px rgba(0,0,0,0.4),
    1px 8px 13px rgba(0,0,0,0.1),
    1px 18px 23px rgba(0,0,0,0.1);
    box-shadow: 1px 4px 3px rgba(0,0,0,0.4);
    border-top: 1px solid black;

    font-size: 2em;
    font-weight: bold;

  }
  .__description {
    display: flex;
    align-items: center;
    justify-content: center;
    padding: 20px;
    font-size: 1.4em;
  }
  .__code-snippet {
    display: flex;
    justify-content: space-around;
    height: fit-content;
  }
  .__example {
    display: flex;
    justify-content: center;
    align-items: center;
    flex: 2;
  }
}

</style>
<style lang="scss">
// My pre-formatted "quoted" code here.
$base-color: #c6538c;
$border-dark: rgba($base-color, 0.88);

.alert {
  border: 1px solid $border-dark;
}
</style>