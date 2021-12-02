<template>

     <div class="serie">
       <div class="flip-card">
      <div class="flip-card-inner">
        <div class="flip-card-front">
          <img
            class="poster"
            :src="`${this.urlImg}${serieData.poster_path}`"
            alt="movieData.poster_path"
          />
        </div>
        <div class="flip-card-back">
          <ul class="p-2">
            <li>{{ serieData.name }}</li>
            <li>{{ serieData.original_name }}</li>
            <li>
              <img
                class="flag"
                :src="
                 require(`../assets/img/${serieData.original_language}.png`)"
                 alt="serieData.original_language"
              />
            </li>
            <li>{{ serieData.vote_average }}</li>
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
  name: 'Serie',
  props: {
    serieData : Object
  }
}
</script>

<style lang="scss">
  .serie{
    height: 300px;
    width: calc(100% / 5 - 10px);
    margin: 5px;
    ul li{
      list-style: none;
      color: white;
      .flag{
        width: 10%;
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