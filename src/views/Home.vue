<template>
  <div class="home">
    <h1>Now playing</h1>
    <div class="home__container">
      <Card
        v-for="movie of movies"
        :key="movie.id"
        :id="movie.id"
        :title="movie.title"
        :imageUrl="movie.poster_path"
      />
    </div>
  </div>
</template>

<script>
import Card from "../components/Card";

export default {
  name: "Home",
  components: {
    Card,
  },
  data() {
    return {
      movies: [],
    };
  },
  created() {
    const base = "https://api.themoviedb.org/3/movie/now_playing";
    const API = `?api_key=${process.env.VUE_APP_API_KEY}`;

    fetch(base + API)
      .then((res) => res.json())
      .then((data) => (this.movies = data.results))
      .catch((e) => console.log(e));
  },
};
</script>

<style scoped>
.home {
  width: 100%;
  text-align: center;
}

.home__container {
  position: absolute;
  left: 0;
  right: 0;
  width: 90%;
  display: flex;
  flex-wrap: wrap;
  align-items: center;
  justify-content: center;
  margin: auto;
}
</style>