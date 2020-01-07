<template>
  <div class="task">
    <h3>Add a task</h3>
    <input id="textInput" type="text" placeholder="Title" v-model="title" />
    <textarea id="textInput" type="text" placeholder="Description" v-model="description" />
    <input id="textInput" type="date" placeholder="Due Date (dd/mm/yyyy)" v-model="date" /><br />
    <button @click="add()">Add Task</button><br />
    <button @click="clearInput()">Clear Data</button>
  </div>
</template>
<script>
export default {
  name: "task",
  props: ["handleEvent"],
  data() {
    return {
      title: "",
      description: "",
      date: ""
    };
  },
  methods: {
    add() {
      let data = {
        title: this.title,
        description: this.description,
        date: this.date
      };
      this.handleEvent(data);
    },
    clearInput() {
      this.title = "",
      this.description = "",
      this.date = ""
    }
  }
};
</script>
<style>
.task {
  width: 250px;
  height: auto;
  background: #b0bec5;
  float: left;
  margin-left: 10px;
  border-radius: 10px;
  height: 350px;
}
h3{
  text-align: center;
}
button{
  background: #0a6ea3;
  border-radius: 5px;
  margin: 15px;
  padding: 10px 20px
}
</style>
