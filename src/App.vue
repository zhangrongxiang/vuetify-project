<template>
  <link href="https://use.fontawesome.com/releases/v5.0.13/css/all.css" rel="stylesheet">
 <div id="app">
  <v-container align="center">
    <v-card width="600px"><h1>To-Do List</h1>
    <v-row class="d-flex flex-grow-1 flex-direction-column" align="center">
      <v-col ><todobtn @todo-added="addToDo"></todobtn></v-col>
    </v-row>
  
  <ul>
    <li v-for="item in ToDoItems" :key="item.id">
    <TodoItem :label="item.label" :done="item.done" :id="item.id"/>
      
    </li>
  </ul></v-card></v-container>
  
  
</div>

</template>

<script>
import { defineComponent,ref } from "vue";
import TodoItem from "./components/ToDoItem.vue";
import uniqueId from "lodash.uniqueid";
import todobtn from "./components/todoforum.vue"
export default {
  name: "app",
  components: {
    TodoItem,
    todobtn,
  },
  data() {
    return {
      ToDoItems: [
        { id: uniqueId("todo-"), label: "Learn Vue", done: false },
        {
          id: uniqueId("todo-"),
          label: "Create a Vue project with the CLI",
          done: true,
        },
        { id: uniqueId("todo-"), label: "Have fun", done: true },
        { id: uniqueId("todo-"), label: "Create a to-do list", done: false },
      ],
    };
  },
  methods: {
    addToDo(theLabel) {
      this.ToDoItems.push({id:uniqueId('todo-'), label: theLabel, done: false});
    },
  },
};


</script>
<style>
.btns{
  width:100%;
}
</style>