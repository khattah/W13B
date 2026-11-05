
<template>
  <div class="tweet-feed">
    <h1>My Tweet Viewer</h1>

    <button @click="toggleView">
      Switch to {{ isGridView ? "List" : "Card" }} View
    </button>

    <div :class="['tweets-container', isGridView ? 'grid-view' : 'list-view']">
      <TweetCard
        v-for="tweet in tweets"
        :key="tweet.id"
        :tweet="tweet"
      />
    </div>
  </div>
</template>

<script>
import TweetCard from "./TweetCard.vue";

export default {
  name: "TweetFeed",

  components: {
    TweetCard
  },

  data() {
    return {
      isGridView: false,

      tweets: [
        {
          id: 1,
          user: "Omer",
          content: "Today I am learning Vue components!",
          date: "November 4, 2026"
        },
        {
          id: 2,
          user: "Ahmed",
          content: "Vue makes building websites easier.",
          date: "November 3, 2026"
        },
        {
          id: 3,
          user: "Sara",
          content: "I love learning JavaScript and Vue!",
          date: "November 2, 2026"
        },
        {
          id: 4,
          user: "John",
          content: "Reusable components save development time.",
          date: "November 1, 2026"
        }
      ]
    };
  },

  methods: {
    toggleView() {
      this.isGridView = !this.isGridView;
    }
  }
};
</script>

<style scoped>
.tweet-feed {
  max-width: 1000px;
  margin: 30px auto;
  padding: 20px;
  text-align: center;
}

button {
  background-color: #2563eb;
  color: white;
  border: none;
  padding: 12px 24px;
  border-radius: 8px;
  cursor: pointer;
  font-size: 16px;
  margin-bottom: 25px;
}

button:hover {
  background-color: #1d4ed8;
}

.tweets-container {
  display: grid;
  gap: 20px;
  text-align: left;
}

.list-view {
  grid-template-columns: 1fr;
}

.grid-view {
  grid-template-columns: repeat(2, minmax(0, 1fr));
}

@media (max-width: 600px) {
  .grid-view {
    grid-template-columns: 1fr;
  }
}
</style>
