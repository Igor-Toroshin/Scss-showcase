<template>
  <div class="intro-page">
Scss
  </div>
</template>

<script>
export default {
  name: 'IntroPage',
  components: {},
  props: {
  },
  computed: {
  }
}
</script>

<style scoped lang="scss">
.intro-page {
  display: flex;
  flex: 1;
  flex-direction: column;

  $secondary: #000;
  background-color: $secondary;
  color: white;
  text-shadow: 1px 4px 3px rgba(0,0,0,0.4),
  1px 8px 13px rgba(0,0,0,0.1),
  1px 18px 23px rgba(0,0,0,0.1);
  box-shadow: 1px 4px 3px rgba(0,0,0,0.4);
  border-top: 1px solid black;

  font-size: 2em;
  font-weight: bold;
}
</style>