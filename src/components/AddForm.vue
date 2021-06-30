<template>
  <div id="add-form">
    <div id="background" v-on:click="Hide"></div>
    <div class="add-form">
      <form class="add-form__content" @submit.prevent="OnSub">
        <label for="name">Имя</label>
        <input type="text" id="name" v-model="login" class="input">
        <label for="comment">Пожелание</label>
        <textarea id="comment" v-model="comment" class="input"></textarea>
        <button type="submit" class="button">Добавить</button>
      </form>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return{
      login:'',
      comment:''
    }
  },
  name: "AddForm",
  methods: {
    OnSub(){
      if (this.login.trim() && this.comment.trim()){
        const newComment = {
          id: Date.now(),
          name: this.login,
          text: this.comment
        }
        const form = document.getElementById("add-form");
        const back = document.getElementById("background");
        form.style.display = 'none';
        back.style.display = 'none';
        this.$emit('add-comment', newComment);
      }
    },

    Hide(){
      const form = document.getElementById("add-form");
      const back = document.getElementById("background");
      form.style.display = 'none';
      back.style.display = 'none';
    }
  }
}
</script>

<style scoped>
#add-form, #background{
  display: none;
}

#background{
  position: fixed;
  top:0;
  bottom: 0;
  left: 0;
  right: 0;
  background-color: rgba(0, 0, 0, 0.5);
}

.add-form__content{
  display: flex;
  flex-direction: column;
  text-align: left;
}

.add-form{
  width: 300px;
  height: 200px;
  position: fixed;
  top:0;
  bottom: 0;
  left: 0;
  right: 0;
  background-color: rgb(225, 225, 224);
  margin: auto;
  padding: 30px;
  border-radius: 10px;
}
.input{
  margin-bottom: 15px;
}

.button{
  width: 100px;
  margin: auto;
  height: 40px;
  font-family: 'Lobster', sans-serif;
  font-size: 20px;
}

.button:hover{
  cursor: pointer;
}
</style>