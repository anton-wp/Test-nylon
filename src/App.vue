<template>
  <div id="app">
    <TestBlock />
  </div>
</template>

<script>
import TestBlock from "@/components/TestBlock";

export default {
  name: "App",
  components: {
    TestBlock,
  },
};
</script>
<style>
@import url(//db.onlinewebfonts.com/c/6fea2948fb886f7fbe31360cb8e5714b?family=Post+Grotesk);
@import url(//db.onlinewebfonts.com/c/a3897dd4acd4ea7bf55831db40dcaab1?family=Monospace+821);

body {
  font-family: "Post Grotesk";
  background-color: rgb(246, 246, 246);
  margin: 0;
}
.monospace {
  font-family: "Monospace 821";
  letter-spacing: -0.085em;
}
</style>

