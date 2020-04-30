<style src="./lightbox.scss"></style>

<template>
  <div class="lightbox" v-if="image" @click="close()">
      <!-- <img :src="image"> -->
      <lightbox-image :image="image"></lightbox-image>
      <div class="lightboxClose">X</div>     
  </div>
</template>

<script>
import './LightboxDirective'
import store from './LightboxStore'
import LightboxImage from './LightboxImage'

export default {
    data () {
        return {
            state: store.state
        }
    },
    components: {
        LightboxImage
    },
    methods: {
        close () {
            store.close()
        }
    },
    computed: {
        image () { 
            if(this.state.index !== false) {
                return this.state.images[this.state.index]
            }
            
        }
    }
}
</script>

<style>

</style>