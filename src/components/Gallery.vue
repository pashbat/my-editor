<template>
  <div class="gallery" @click="nextImage">
      <img :src="images[currentImage]">
  </div>
</template>
<script>

export default {
  name: 'Gallery',

  data() {
    return {
      images: ['http://placeimg.com/300/300/animals', 'http://placeimg.com/300/300/arch', 'http://placeimg.com/300/300/nature', 'http://placeimg.com/300/300/people', 'http://placeimg.com/300/300/tech', ],
      currentImage: 0
    }
  },
  watch: {
    currentImage(oldVal, newVal) {

    }
  },
  methods: {
    nextImage() {
      let vm = this
      if(vm.currentImage == vm.images.length - 1) {
        vm.currentImage = 0;
      }
      else {
        vm.currentImage++
      }
    }
  }  
}
</script>
<style lang="scss" scoped>
.gallery {
  width: 320px;
  height: 320px;
  cursor: pointer;
}
img {
  width: 100%;
  height: auto;
}
</style>
