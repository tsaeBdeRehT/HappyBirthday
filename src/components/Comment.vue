<template>
 <div class="comment">
   <span class="name">{{comment.name}}</span>
   <p>{{comment.text}}</p>
 </div>
</template>

<script>
export default {
  name: "Comment",
  props: {
    comment: {
      type: Object,
      required: true
    }
  }
}
</script>

<style scoped>
.comment{
  background-color: rgba(144,238,144,0.5);
  width: 200px;
  height: 150px;
  margin: 20px;
  display: inline-block;
  word-wrap: break-word;
  padding: 10px;
  white-space: normal;
  overflow: hidden;
  text-align: left;
  border-radius: 10px;
}
.name{
  border-bottom: 1px solid rgba(144, 255, 144, 0.5);
}

p {
  margin-bottom: 0;
}
</style>