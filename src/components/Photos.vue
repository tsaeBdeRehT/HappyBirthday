<template>
  <div class="viewport">
    <button class="nav left" type="button" v-on:click="OnScrollLeft">Туда</button>
    <button class="nav right" type="button" v-on:click="OnScrollRight">Туда</button>
    <div class="photo-section" id="photo-section">
      <PhotoCard
          v-for="photo of photos" :key="photo.id"
          v-bind:photo="photo"
      />
    </div>
  </div>
</template>

<script>
import PhotoCard from "@/components/PhotoCard";
export default {
  name: "Photos",
  props: ['photos'],
  components: {
    PhotoCard
  },
  methods: {
    OnScrollRight() {
      const el = document.getElementById('photo-section');
      el.scroll({
        left: el.scrollLeft + 400,
        behavior: 'smooth'
      });
    }
    ,
    OnScrollLeft() {
      const el = document.getElementById('photo-section');
      el.scroll({
        left: el.scrollLeft - 400,
        behavior: 'smooth'
      });
    }
  }
}
</script>

<style scoped>
.viewport{
  width: 1080px;
  position: relative;
}

.photo-section{
  margin: auto;
  width: 950px;
  overflow: hidden;
  overflow-x: scroll;
  white-space: nowrap;
}

.photo-section::-webkit-scrollbar{
  width: 0;
}

.nav{
  height: 300px;
}
</style>