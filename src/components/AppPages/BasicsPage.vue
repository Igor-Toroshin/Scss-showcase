<template>
  <AppPage :title="title" :description="description" :code-snippets="codeSnippets">
    <template v-slot:example>
      <div class="example-wrapper">
        <div>
          <button class="button">button</button>
        </div>
        <div>
          <div class="wrapper">
            <div class="top-button">
              <button class="button">
                <span>button-span</span>
              </button>
            </div>
          </div>
        </div>
        <div>
          <button class="button button-hover">button</button>
        </div>
      </div>
    </template>
  </AppPage>
</template>

<script>
import AppPage from "@/components/AppPage";
export default {
  name: "BasicsPage",
  components: {AppPage},
  computed: {
    title() {
      return 'Variables, Nesting and Parent Selector';
    },
    description() {
      return 'Scss wants to make your life easier. Rather than repeating the same selectors over and over again, you can write one style rules inside another. Scss will automatically combine the outer rule’s selector with the inner rule’s.';
    },
    codeSnippets() {
      return [`// Variables.
  $base-color: #4bdef8;
  $border-dark: #4b88f8;
  $border-radius: 10px;

  .button {
    background: $base-color;
    border: 1px solid $border-dark;
    border-radius: $border-radius;
    ...
  }
  `,`// Nesting.
  .wrapper {
    .top-button {
      button {
        span {
          color: black;
        }
      }
    }
  }`,`// Parent selector &.
  .button-hover {
    &:hover {
      background-color: #4b88f8;
    }

    &::after {
      content: ' hover';
    }
  }
  <div>
    <button class="button button-hover">button</button>
  </div>`]
    }
  }
}
</script>

<style scoped lang="scss">
$base-color: #4bdef8;
$border-dark: #4b88f8;
$border-radius: 10px;

.button {
  background: $base-color;
  border: 1px solid $border-dark;
  border-radius: $border-radius;
  box-shadow: $base-color 0 10px 20px -10px;
  color: #FFFFFF;
  font-size: 20px;
  font-weight: 700;
  line-height: 24px;
  margin: 5px;
  padding: 8px 16px;
  width: fit-content;
}

.wrapper {
  .top-button {
    button {
      span {
        color: black;
      }
    }
  }
}

.example-wrapper {
  display: flex;
  flex: 1;
  flex-direction: row;
  justify-content: space-around;
}

.button-hover {
  &:hover {
    background-color: #4b88f8;
  }

  &::after {
    content: ' hover';
  }
}
</style>