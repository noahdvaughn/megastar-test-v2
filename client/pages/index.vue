<template>
    
  <div class="main-body-background">

    <Header :viewingOpen="viewingOpen" @setViewingOpen="onSetViewingOpen"/>
    <v-form>
    <v-text-field label="Search Todo's" class="main-search"></v-text-field>
    </v-form>

    <div class="main-feed">
      <li v-for="todo in todos">
        <ToDoItem v-if="todo.completed === viewingOpen" :item="todo"/>
        <ToDoItem v-if="todo.completed === viewingOpen" :item="todo"/>
      </li>
    </div>
    
  </div>
</template>

<script>
  import {ref} from 'vue'
export default{
  setup(){
    let todos = ref([])
    let originalTodos = []
    let viewingOpen = ref(true)
    return{
      todos, originalTodos, viewingOpen
    }
  },
  
  mounted() {
    this.GetToDos()
  },
  methods: {
    async GetToDos(){
      const res = await (await fetch('https://jsonplaceholder.typicode.com/users/1/todos')).json()
      this.todos = res
      this.originalTodos = res
    },
    onSetViewingOpen(bool){
      this.viewingOpen = bool
    }
  },

}

</script>



<style>
.main-body-background{
    background-color: #060417;
    height: 100vh;
    width: 100vw;
    text-align: center;
    display: flex;
    flex-direction: column;
    /* justify-content: center; */
    align-items: center;
}
.main-search{
  background-color: #2a2639;
  color: white;
  width: 90vw;
  border-radius: 1rem;
  margin-top: 1rem;
  margin-bottom: 1rem;
}
.main-feed{
  overflow-y: scroll;

}

</style>