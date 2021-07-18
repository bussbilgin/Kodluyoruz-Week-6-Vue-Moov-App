<template>
  <div class="movie">
    <div class="button">
      <router-link to="/" class="button-back">
        <p>ANASAYFAYA DÖN</p>
      </router-link>
    </div>

    <div class="movie-detail">
      <figure>
        <img
          :src="
            movie.Poster !== 'N/A'
              ? movie.Poster
              : 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/ac/No_image_available.svg/2048px-No_image_available.svg.png'
          "
          alt="Movie Poster"
          class="featured-img"
        />
      </figure>

      <div class="content">
        <h2>{{ movie.Title }}</h2>
        <p><b>IMDB:</b> {{ movie.imdbRating }}</p>
        <p><b>Gentle:</b> {{ movie.Genre }}</p>
        <p><b>Year:</b> {{ movie.Year }}</p>

        <p>{{ movie.Plot }}</p>
      </div>
    </div>
  </div>
</template>

<script>
import { ref, onBeforeMount } from "vue";
import { useRoute } from "vue-router";
import env from "@/env.js";

export default {
  setup() {
    const movie = ref({});
    const route = useRoute();

    onBeforeMount(() => {
      fetch(
        `http://www.omdbapi.com/?apikey=${env.apiKey}&i=${route.params.id}&plot=full`
      )
        .then((response) => response.json())
        .then((data) => {
          movie.value = data;
        });
    });

    return {
      movie,
    };
  },
};
</script>

<style lang="scss">
.button {
  margin-top: 20px;
  display: flex;
  justify-content: center;

  .button-back {
    p {
      width: 400px;
      height: 70px;
      font-size: 20px;
      font-weight: 600;
      border-radius: 8px;
      display: flex;
      justify-content: center;
      align-items: center;
      background-color: #d3d3d3;
    }
  }
}

.movie-detail {
  margin: 150px;
  display: flex;
  align-items: flex-start;

  figure {
    img {
      margin-right: 25px;
      display: block;
      max-width: 250px;
      margin-bottom: 16px;
      border-radius: 8px;
    }
  }

  .content {
    margin-top: -10px;
    h2 {
      color: #000;
      font-size: 30px;
      font-weight: 600;
      margin-bottom: 16px;
    }

    p {
      color: #000;
      font-size: 18px;
      line-height: 1.4;
      margin-bottom: 16px;
    }
  }
}
</style>