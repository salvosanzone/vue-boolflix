<template>

  <div class="movie">
    <div class="flip-card">
      <div class="flip-card-inner">
        <div class="flip-card-front">
          <img
            class="poster"
            :src="`${this.urlImg}${movieData.poster_path}`"
            alt="movieData.poster_path"
          />
        </div>
        <div class="flip-card-back">
          <ul class="p-2">
            <li>{{ movieData.title }}</li>
            <li>{{ movieData.original_title }}</li>
            <li>
              <img
                class="flag"
                :src="
                 require(`../assets/img/${movieData.original_language}.png`)"
                 alt="movieData.original_language"
              />
            </li>
            <li>{{ movieData.vote_average }}</li>
            <li>
              <p class="overflow-hidden">{{ movieData.overview }}</p>
            </li>
          </ul>
        </div>
      </div>
    </div>
  </div>

</template>

<script>
export default {
  name: "Movie",
  props: {
    movieData: Object,
  },
  data() {
    return {
      urlImg: "https://image.tmdb.org/t/p/w342/",
    };
  },
};
</script>

<style lang="scss">
.movie {
  height: 300px;
  width: calc(100% / 5 - 10px);
  margin: 5px;
  overflow: hidden;
  ul li {
    list-style: none;
    color: white;
    .flag {
      width: 10%;
    }
    p{
      font-size: 10px;
    }
    
  }
}

.flip-card {
  height: 100%;
  width: 100%;
  perspective: 1000px;
  background-color: transparent;
}

.flip-card-inner {
  position: relative;
  width: 100%;
  height: 100%;
  text-align: center;
  transition: transform 0.6s;
  transform-style: preserve-3d;
  box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2);
}

.flip-card:hover .flip-card-inner {
  transform: rotateY(180deg);
}

.flip-card-front {
  position: absolute;
  -webkit-backface-visibility: hidden;
  backface-visibility: hidden;
  object-fit: fill;

.poster {
  max-width: 100%;
  max-height: 100%;
  object-fit: fill;
}
}
.flip-card-back {
  width: 100%;
  height: 100%;
  position: absolute;
  -webkit-backface-visibility: hidden;
  backface-visibility: hidden;
}

.flip-card-front {
  background-color: #bbb;
  color: black;
}

.flip-card-back {
  background-color: black;
  color: white;
  transform: rotateY(180deg);
}
</style>