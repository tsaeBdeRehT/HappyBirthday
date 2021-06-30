<template>
  <div id="app">
    <Header/>
    <Reason1
    v-bind:photos="photos"
    />
    <Reason2/>
    <Reason3 v-bind:comments="comments" @add-comment="AddComment"/>
  </div>
</template>

<script>

import Reason3 from "@/components/Reason3";
import Reason2 from "@/components/Reason2";
import Header from "@/components/Header";
import Reason1 from "@/components/Reason1";

export default {
  name: 'App',
  data() {
    return {
      photos: [
        {id: 1, sr: require("./assets/1.jpg"), text: "Новогодняя версия"},
        {id: 2, sr: require("./assets/2.jpg"), text: "В работе"},
        {id: 3, sr: require("./assets/3.jpg"), text: "Модная версия"}
      ],
      comments: [
        {id: 1, name: 'Goose', text: 'HUffffffffffffffffffffffffI'},
        {id: 2, name: 'Goose', text: 'HUI'},
        {id: 3, name: 'Goose', text: 'HUI'}
      ]
    }
  },
  methods:{
    AddComment(newComment) {
      this.comments.push(newComment);
    }
  },
  components: {
    Reason3,
    Reason2,
    Reason1,
    Header
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Dancing+Script:wght@700&family=Lobster&display=swap');
#app {
  font-family: 'Lobster', sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  width: 1140px;
  padding: 30px;
  margin: auto;
}

body {
  margin: 0;
  height: 1000px;
  background-image: url("./assets/header.jpg");
  background-size: cover;
  background-repeat: no-repeat;
  background-attachment: fixed;
}
</style>
