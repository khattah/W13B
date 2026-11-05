
<template>
  <div class="tweet-card">
    <h3>{{ tweet.user }}</h3>
    <p>{{ tweet.content }}</p>
    <small>{{ tweet.date }}</small>
  </div>
</template>

<script>
export default {
  name: "TweetCard",
  props: {
    tweet: {
      type: Object,
      required: true
    }
  }
};
</script>

<style scoped>
.tweet-card {
  background-color: white;
  border: 1px solid #ddd;
  border-radius: 10px;
  padding: 20px;
  box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
  height: 100%;
  box-sizing: border-box;
}

h3 {
  color: #2563eb;
  margin-top: 0;
}

p {
  font-size: 16px;
  line-height: 1.5;
}

small {
  color: #777;
}
</style>
