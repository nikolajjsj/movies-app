<template>
  <div class="movie" v-if="movie">
    <img class="movie__backdrop" :src="backdropUrl" alt="movie poster" />
    <h1 class="movie__title">{{ movie.title }}</h1>
    <h3 class="movie__overview">{{ movie.overview }}</h3>
    <h3 class="movie__release">Released: {{ movie.release_date }}</h3>
    <h3 class="movie__score">Score: {{ movie.vote_average }}/10</h3>
    <a class="movie__imdb" :href="imdbUrl"> IMDb </a>
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
      movie: {},
    };
  },
  computed: {
    backdropUrl: function () {
      return "http://image.tmdb.org/t/p/w300/" + this.movie.poster_path;
    },
    imdbUrl: function () {
      return "http://imdb.com/title/" + this.movie.imdb_id;
    },
  },
  created() {
    const base = `https://api.themoviedb.org/3/movie/${this.$route.params.id}`;
    const API = `?api_key=${process.env.VUE_APP_API_KEY}`;

    fetch(base + API)
      .then((res) => res.json())
      .then((data) => (this.movie = data))
      .catch((e) => console.log(e));
  },
};
</script>

<style scoped>
.movie {
  position: absolute;
  left: 0;
  right: 0;
  margin: 2rem auto;
  padding: 2rem;
  width: 60%;
  display: flex;
  flex-direction: column;
  align-items: center;
}

.movie__backdrop {
  height: 250px;
  width: 250px;
  object-fit: cover;
  border-radius: 50%;
}

.movie__title {
  text-align: center;
}

.movie__overview {
  text-align: center;
}

.movie__imdb {
  text-decoration: none;
  background: #2c3e50;
  color: white;
  font-weight: bolder;
  font-size: 2rem;
  border-radius: 12px;
  padding: 0.5rem 1rem;
}
</style>