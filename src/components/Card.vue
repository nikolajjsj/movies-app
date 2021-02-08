<template>
  <router-link class="card" :to="`/movie/${id}`">
    <img class="card__image" :src="posterUrl" alt="movie poster" />
    <h2 class="card__title">{{ title }}</h2>
  </router-link>
</template>

<script>
export default {
  name: "Card",
  props: {
    id: Number,
    title: String,
    imageUrl: String,
  },
  computed: {
    posterUrl: function () {
      return "http://image.tmdb.org/t/p/w300" + this.imageUrl;
    },
  },
};
</script>

<style>
.card {
  max-width: 80%;
  border-radius: 8px;
  border: 2px solid #2c3e50;
  margin: 0.5rem;
  text-decoration: none;
  color: inherit;
}

.card:hover {
  background: #2c3e50;
  color: white;
}

.card__image {
  width: 100%;
  object-fit: cover;
  border-top-left-radius: 6px;
  border-top-right-radius: 6px;
}

.card__title {
  text-align: center;
}
</style>