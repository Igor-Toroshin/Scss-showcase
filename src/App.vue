<template>
  <div class="scroll-container">
<!--    <IntroPage class="scroll-area"></IntroPage>-->
    <BasicsPage class="scroll-area"></BasicsPage>
    <ExtendPage class="scroll-area"></ExtendPage>
    <MixinPage class="scroll-area"></MixinPage>
    <InterpolationPage class="scroll-area"></InterpolationPage>
<!--    flow control-->
    <IfAndElsePage class="scroll-area"></IfAndElsePage>
<!-- at rules-->
    <EachPage class="scroll-area"></EachPage>
    <ForPage class="scroll-area"></ForPage>
<!--    <WhilePage class="scroll-area"></WhilePage>-->

    <function-page class="scroll-area"></function-page>
    <ColorModulePage class="scroll-area"></ColorModulePage>
    <MathModulePage class="scroll-area"></MathModulePage>
    <StringModulePage class="scroll-area"></StringModulePage>
  </div>
</template>

<script>
import BasicsPage from "@/components/AppPages/BasicsPage";
import MixinPage from "@/components/AppPages/MixinPage";
import InterpolationPage from "@/components/AppPages/InterpolationPage";
import ExtendPage from "@/components/AppPages/ExtendPage";
import IfAndElsePage from "@/components/AppPages/IfAndElsePage";
import FunctionPage from "@/components/AppPages/FunctionPage";
import EachPage from "@/components/AppPages/atRules/EachPage";
// import WhilePage from "@/components/AppPages/atRules/WhilePage";
import ForPage from "@/components/AppPages/atRules/ForPage";
import ColorModulePage from "@/components/AppPages/modules/ColorModulePage";
import MathModulePage from "@/components/AppPages/modules/MathModulePage";
import StringModulePage from "@/components/AppPages/modules/StringModulePage";
// import IntroPage from "@/components/IntroPage";

export default {
  name: 'App',
  components: {
    // IntroPage,
    StringModulePage,
    MathModulePage,
    ColorModulePage,
    ForPage,
    // WhilePage,
    EachPage,
    FunctionPage,
    IfAndElsePage,
    ExtendPage,
    InterpolationPage,
    MixinPage,
    BasicsPage,
  },
  computed: {
  }
}
</script>

<style lang="scss">
html {
  padding:0;
}

.scroll-container,
.scroll-area {
  max-width: 100vw;
  height: 100vh;
}

.scroll-container {
  overflow: auto;
  overflow-x: hidden;
  scroll-snap-type: y mandatory;
}

.scroll-area {
  color: white;
  scroll-snap-align: start;
}
</style>
