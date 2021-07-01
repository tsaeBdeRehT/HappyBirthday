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
        {id: 3, sr: require("./assets/3.jpg"), text: "Модная версия"},
        {id: 4, sr: require("./assets/4.jpg"), text: "Боевой режим"},
        {id: 5, sr: require("./assets/5.jpg"), text: "Режим мага"},
        {id: 6, sr: require("./assets/6.jpg"), text: "Расширенная версия"},
        {id: 7, sr: require("./assets/7.jpg"), text: "Вкусное дополнение"}
      ],
      comments: null
    }
  },
  mounted() {
    fetch("http://localhost:8000/api/comments", {
      method: "GET",
      headers: {
        "Content-Type": "application/json"
      }
    }).then((res) => {
      if (res.ok){
        res.json().then((res) => {
          this.comments = res;
        })
      }
    })
  },
  methods:{
    AddComment(newComment) {
      fetch("http://localhost:8000/api/comments", {
        method: "POST",
        headers: {
          "Content-Type": "application/json"
        },
        body: JSON.stringify({
          name: newComment.name,
          text: newComment.text
        })
      }).then((res) => {
        if (res.ok) this.comments.push(newComment);
      })
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
