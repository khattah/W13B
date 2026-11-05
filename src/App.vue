
<template>
  <div id="app">
    <TweetFeed />
  </div>
</template>

<script>
import TweetFeed from "./components/TweetFeed.vue";

export default {
  name: "App",
  components: {
    TweetFeed
  }
};
</script>

<style>
body {
  margin: 0;
  background-color: #f1f5f9;
  font-family: Arial, sans-serif;
}

#app {
  min-height: 100vh;
}
</style>
