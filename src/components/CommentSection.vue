<template>
  <div class="viewport">
    <button id="left" class="nav left" v-on:click="OnScrollLeft">Туда</button>
    <button id="right" class="nav right" v-on:click="OnScrollRight">Туда</button>
    <div id="comment-section" class="comment-section">
      <Comment v-for="comment of comments" :key="comment.id"
               v-bind:comment="comment"/>
    </div>
  </div>

</template>

<script>
import Comment from "@/components/Comment";
export default {
  name: "CommentSection",
  props: ['comments'],
  components: {Comment},
  methods: {
    OnScrollRight() {
      const el = document.getElementById('comment-section');
      el.scroll({
        left: el.scrollLeft + 400,
        behavior: 'smooth'
      });
    }
    ,
    OnScrollLeft() {
      const el = document.getElementById('comment-section');
      el.scroll({
        left: el.scrollLeft - 400,
        behavior: 'smooth'
      });
    }
  }
}
</script>

<style>
.viewport{
  width: 1080px;
  position: relative;
}

.comment-section{
  margin: auto;
  width: 950px;
  overflow: hidden;
  overflow-x: scroll;
  white-space: nowrap;
}

.comment-section::-webkit-scrollbar{
  width: 0;
}

.nav{
  background-color: rgba(225, 225, 224, 0.3);
  font-family: 'Lobster', sans-serif;
  font-size: 25px;
  border: none;
  border-radius: 5px;
  position: absolute;
  height: 170px;
  margin-top: 20px;
}

.left {
  left: 0;
}

.right{

  right: 0;
}

.nav:hover{
  cursor: pointer;
  background-color: rgba(225, 225, 224, 0.5);
}
</style>