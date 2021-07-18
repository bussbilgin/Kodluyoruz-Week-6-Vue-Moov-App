<template>
  <section class="section">
    <form @submit.prevent="SearchMovies()" class="search-box">
      <input
        type="text"
        placeholder="What are you looking for?"
        v-model="search"
      />&emsp;
      <input type="submit" value="Search" />
    </form>

    <nav class="section__nav">
      <a href="#">TV Series</a>
      <a href="#">&emsp;&emsp;Movies</a>
      <a href="#">&emsp;&emsp;Animes</a>
    </nav>

    <div v-if="movies.length === 0 && highlights.length !== 0" class="feature">
      <div class="feature-card">
        <router-link to="/movie/tt0903747">
          <img
            src="/breakingbad-img.jpg"
            alt="Breaking Bad Poster"
            class="featured-img"
          />
          <div class="detail">
            <h3>Breaking Bad</h3>
            <p>
              When chemistry teacher Walter White is diagnosed with Stage III
              cancer and given only two years to live, he decides he has nothing
              to lose.
            </p>
          </div>
        </router-link>
      </div>
    </div>

    <div
      v-if="movies.length === 0 && highlights.length !== 0"
      class="featured-movies"
    >
      <h2 class="featured-header">Featured Movies</h2>
      <div class="movies-list">
        <div class="movie" v-for="movie in highlights" :key="movie.imdbID">
          <router-link :to="'/movie/' + movie.imdbID" class="movie-link">
            <div class="product-image">
              <img
                :src="
                  movie.Poster !== 'N/A'
                    ? movie.Poster
                    : 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/ac/No_image_available.svg/2048px-No_image_available.svg.png'
                "
                alt="Movie Poster"
              />
              <div class="type">{{ movie.Type }}</div>
            </div>
            <div class="detail">
              <p class="year">{{ movie.Year }}</p>
              <h3>{{ movie.Title }}</h3>
            </div>
          </router-link>
        </div>
      </div>
    </div>

    <div class="movies-list">
      <div class="movie" v-for="movie in movies" :key="movie.imdbID">
        <router-link :to="'/movie/' + movie.imdbID" class="movie-link">
          <div class="product-image">
            <img
              :src="
                movie.Poster !== 'N/A'
                  ? movie.Poster
                  : 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/ac/No_image_available.svg/2048px-No_image_available.svg.png'
              "
              alt="Movie Poster"
            />
            <div class="type">{{ movie.Type }}</div>
          </div>
          <div class="detail">
            <p class="year">{{ movie.Year }}</p>
            <h3>{{ movie.Title }}</h3>
          </div>
        </router-link>
      </div>
    </div>
  </section>
</template>

<script>
import { ref } from "vue";
import env from "@/env.js";
import { onMounted } from "vue";

export default {
  setup() {
    const search = ref("");
    const movies = ref([]);
    const highlights = ref([]);

    const SearchMovies = () => {
      if (search.value != "") {
        fetch(`http://www.omdbapi.com/?apikey=${env.apiKey}&s=${search.value}`)
          .then((response) => response.json())
          .then((data) => {
            movies.value = data.Search;
            search.value = "";
          });
      }
    };

    const getNaruto = () => {
      fetch(`http://www.omdbapi.com/?apikey=${env.apiKey}&s=movie`)
        .then((response) => response.json())
        .then((data) => {
          highlights.value = data.Search;
          console.log(data);
        });
    };

    onMounted(() => {
      getNaruto();
    });

    return {
      search,
      movies,
      highlights,
      SearchMovies,
      getNaruto,
    };
  },
};
</script>
