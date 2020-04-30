<template>
  <div id="app">
    <section class="sectionLightbox">
      <a :href="'https://picsum.photos/id/'+ n +'/800/600'" v-lightbox v-for="n in 9" :key="n" class='bigImg'>
        <img :src="'https://picsum.photos/id/'+ n +'/150/150'" class="thumbnail">
      </a>
      <lightbox></lightbox>
    </section>
  </div>
</template>

<script>
import Lightbox from './components/lightbox/Lightbox'

export default {
  name: 'App',
  components: {
    Lightbox
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.sectionLightbox {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-around;
}

.thumbnail {
  border-radius: 75px;
  margin: 15px;
}

.thumbnail:hover {
  transition: transform 500ms ease-in-out;
  transform: scale(1.3);
}

</style>
