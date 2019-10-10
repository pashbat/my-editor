<template>
  <div class="editor">
    <div class="editor-header">
       <button class="button" @click="insertGallery">insert component</button> 
    </div>
    <div class="editor-body" ref="editorBody" contenteditable='true'>
      <p>Lorem, ipsum dolor sit amet consectetur adipisicing elit. Reprehenderit quisquam cumque architecto voluptatem et, fugiat corporis, deleniti atque saepe tempora, quidem eum numquam. Quasi esse, accusamus alias tempore doloremque rerum?</p>
      
    </div>
  </div>
</template>

<script>
import Vue from 'vue'
import Gallery from './Gallery.vue'

export default {
  name: 'Editor',
  components: {
    Gallery
  },
  props: {
    msg: String
  },
  methods: {
    insertGallery(){
      var GalleryClass = Vue.extend(Gallery)
      var gallery = new GalleryClass()
      gallery.$mount() 
      this.$refs.editorBody.appendChild(gallery.$el)
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.editor-body {
  width: 320px;
  margin: 1rem auto;
  border: 1px solid black;
  outline: 0;
  padding: 1rem;
}

</style>
