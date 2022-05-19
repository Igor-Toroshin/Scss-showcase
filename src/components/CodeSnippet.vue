<template>
<pre>
<code class="language-css scrollable">
  {{ code }}
</code>
</pre>

</template>

<script>
export default {
  name: "CodeSnippet",
  props: {
    code: {
      required: true,
      type: String
    }
  }
}
</script>

<style scoped lang="scss">
pre {
  border: solid 1px black;
  width: fit-content ;
  overflow: auto;
  padding-inline-end: 1rem;
  background-color: #eee;
  box-shadow: 3px 3px 4px rgba(0,0,0,0.2);
}

.scrollable {
  overflow-y: scroll;
  overflow-x: scroll;
}
</style>