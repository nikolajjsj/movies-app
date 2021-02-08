<template>
  <div class="about">
    <h1>About App</h1>
    <h2>Vue.js app displaying data from:</h2>
    <a
      class="about__link"
      href="https://developers.themoviedb.org"
      target="_blank"
      ><strong>https://developers.themoviedb.org</strong>
    </a>
    <h2>Created by Nikolaj Johannes Skole Jensen</h2>
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
  width: 100%;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}

.about__link {
  text-decoration: none;
  color: inherit;
}
</style>