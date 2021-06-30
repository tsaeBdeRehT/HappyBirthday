<template>
  <div class="scroll_line">
      <PhotoCard
          v-for="photo of photos" :key="photo.id"
          v-bind:photo="photo"
      />
  </div>
</template>

<script>
import PhotoCard from "@/components/PhotoCard";
export default {
  name: "Photos",
  props: ['photos'],
  components: {
    PhotoCard
  }
}
</script>

<style scoped>
.scroll_line{
  overflow: hidden;
}
</style>