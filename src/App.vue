<template>
  <div class="wrapper">
    <div class="main">
      <h1>To Do List</h1>
      <ComponentPending title="Pending" :listTasks="listTasks"></ComponentPending>
      <ComponentPending title="In Progress"></ComponentPending>
      <ComponentPending title="Completed"></ComponentPending>
      <ComponentTask :handleEvent="handleEvent"></ComponentTask>
    </div>
  </div>
</template>
<script>
import ComponentPending from "./components/Pending";
import ComponentTask from "./components/Task";
export default {
  components: {
    ComponentPending,
    ComponentTask
  },
  data() {
    return {
      listTasks: {},
    };
  },
  methods: {
    handleEvent(valueData) {
      this.listTasks = valueData;
    }
  }
};
</script>
<style>
.wrapper {
  width: 1070px;
  height: 500px;
  background: #b0bec5;
  padding-top: 20px;
}
h1{
  text-align: center;
  color: white;
  padding-top: 10px; 
}
.main {
  width: 1050px;
  height: 450px;
  background: #263238;
  margin-left: 10px;
}
</style>
