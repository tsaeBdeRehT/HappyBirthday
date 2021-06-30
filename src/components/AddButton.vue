<template>
  <button id="add-button" type="button" v-on:click="ShowForm">Добавить пожелание</button>
</template>

<script>
export default {
  name: "AddButton",
  methods: {
    ShowForm(){
      const form = document.getElementById("add-form");
      const back = document.getElementById("background");
      form.style.display = 'block';
      back.style.display = 'block';
    }
  }
}
</script>

<style>
#add-button{
  background-color: rgba(225, 225, 224, 0.5);
  margin: 20px;
  font-family: 'Lobster', sans-serif;
  height: 40px;
  font-size: 25px;
  border: 1px solid rgba(225, 225, 224, 0.5);
  border-radius: 10px;
}

#add-button:hover{
  cursor: pointer;
  background-color: rgba(225, 225, 224, 0.7);
}
</style>