<template>
      <figure class="photo">
        <img :src="photo.sr" height="300">
        <figcaption>{{photo.text}}</figcaption>
      </figure>
</template>

<script>
export default {
  name: "PhotoCard",
  props: {
    photo:{
      type: Object,
      required: true
    }
  }
}
</script>

<style scoped>
.photo{
  width: fit-content;
  margin: 20px;
  display: inline-block;
}
</style>