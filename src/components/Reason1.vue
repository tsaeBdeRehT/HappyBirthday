<template>
  <div id="reason1">
    <h2>Внешний вид</h2>
    <h6>Просто посмотрите на эту лапочку</h6>
    <Photos
    v-bind:photos="photos"
    />
  </div>
</template>

<script>
import Photos from "@/components/Photos";
export default {
  name: "Reason1",
  props: ['photos'],
  components: {Photos}
}
</script>

<style>
#reason1{
  font-size: 30px;
}
</style>