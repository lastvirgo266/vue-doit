<!-- 그런데 이런식으로 처리하면 정적으로 처리됨 -> 즉각반응 X -->

<template>
  <section>
    <ul>
      <li v-for="todoItem in todoItems" v-bind:key="todoItem">{{todoItem}}</li>
    </ul>
  </section>

</template>

<script>
export default {
  name: "TodoList",

  data(){
    return{
      todoItems:[]
    }
  },

  created() {
    if (localStorage.length > 0){
      for(var i = 0; i<localStorage.length; i++){
        this.todoItems.push(localStorage.key((i)));
      }
    }
  },

}
</script>

<style scoped>

</style>