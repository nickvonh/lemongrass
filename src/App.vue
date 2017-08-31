<template>
  <div id="app" class="layout">
    <section class="hero is-large is-light slanted">
      <div class="hero-body logoHead" style="background-image : url('./dist/photos/header.png')">
      </div>
    </section>
    <section class="hero is-large is-light">
      <h2 class="title">Menu</h2>
      <div class="section" v-for="(each, index) in menu" :key="index">
        <menu-block :menu="each" :title="index"></menu-block>
        <hr>
      </div>
    </section>
    <section class="hero is-large">
      <h2 class="title">Image Gallery</h2>
      <div class="gallery">
        <div class="image-tile" v-for="(each, index) in photos" :key="index">
          <img :src="`./dist/photos/${each}`"/>
        </div>
      </div>
    </section>
  </div>
</template>

<script>
import pho from './assets/menu/pho.json'
import appetizers from './assets/menu/appetizers.json'
import specials from './assets/menu/specialty_dishes.json'
import photos from './assets/photos/photos.json'

import MenuBlock from './components/MenuBlock.vue'
export default {
  name: 'app',
  components: {MenuBlock},
  data () {
    return {
      menu : {
        appetizers,
        pho,
        specials,
      },
      photos: photos
    }
  }
}
</script>

<style lang="stylus">
@import '../node_modules/bulma-stylus/bulma.styl'
.logoHead.hero-body
  background-size 40%
  background-repeat no-repeat
  background-position 50% 15%
  background-attachment fixed
  margin-bottom 50px
.title,.sub-title
  text-align center
  text-transform uppercase
.gallery
  display flex
  flex-flow row wrap
  padding 0 15vw
  .image-tile
    width 17vw
    padding 1vw

.slanted
  position relative
.slanted:after 
  content ''
  display block
  position absolute
  width 100%
  height 350px
  background white
  -ms-transform skewY(-4deg)
  transform skewY(-4deg)
  z-index 0
.slanted:after
  bottom -300px
.title
  z-index 1

@media (max-width: 1200px){
  #app{
    font-size: 1.5em;
  }

  .gallery{
    padding 0 5vw
  }
  .gallery .image-tile{
    width 45vw
  }
}
 
</style>
