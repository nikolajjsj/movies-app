<template>
  <div class="about">
    <h1 class="about__title">About App</h1>
    <h3 class="about__subtitle">Vue.js app displaying data from:</h3>
    <a
      class="about__link"
      href="https://developers.themoviedb.org"
      target="_blank"
      ><strong>https://developers.themoviedb.org</strong>
    </a>
    <h3 class="about__subtitle">Created by Nikolaj Johannes Skole Jensen</h3>
    <a
      class="about__link"
      href="https://github.com/nikolajjsj/movies-app"
      target="_blank"
      ><strong>https://github.com/nikolajjsj/movies-app</strong>
    </a>
  </div>
</template>

<style scoped>
.about {
  width: 80%;
  position: absolute;
  top: 60px;
  left: 0;
  right: 0;
  bottom: 0;
  margin: auto;
  text-align: center;
}

.about__subtitle {
  margin: 1rem;
}

.about__subtitle {
  margin-top: 2rem;
}

.about__link {
  text-decoration: none;
  color: inherit;
}
</style>