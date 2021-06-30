<template>
  <div id="reason3">
    <h2>Пожелания пользователей к новой версии</h2>
    <CommentSection v-bind:comments="comments"/>
    <AddButton/>
    <AddForm @add-comment="AddComment"/>
  </div>
</template>

<script>
import AddForm from "@/components/AddForm";
import AddButton from "@/components/AddButton";
import CommentSection from "@/components/CommentSection";
export default {
  name: "Reason3",
  components: {AddForm, AddButton, CommentSection},
  props:['comments'],
  methods: {
    AddComment(newComment){
      this.$emit('add-comment', newComment);
    }
  }
}
</script>

<style scoped>
#reason3{
  font-size: 30px;
}
</style>