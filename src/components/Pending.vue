<template>
  <div class="pending">
    <h3>{{ title }}</h3>
    <div class="row">
      <div class="col-3">
        <draggable class="list-group" :list="list1" group="people" @change="log">
          <div class="list-group-item" v-for="element in list1" :key="element">
            {{ "Title:" + element.title }}
            <br />
            {{
            "Description:" + element.description
            }}
            <br />
            {{ "Date:" + element.date }}
          </div>
        </draggable>
      </div>
    </div>
  </div>
</template>
<script>
import draggable from "vuedraggable";
export default {
  props: ["title", "listTasks"],
  name: "two-lists",
  display: "Two Lists",
  order: 1,
  components: {
    draggable
  },
  data() {
    return {
      list1: []
    };
  },
  watch: {
    listTasks: {
      deep: true,
      handler() {
        this.list1.push(this.listTasks);
      }
    }
  }
};
</script>
<style>
.pending {
  width: 250px;
  height: auto;
  background: #b0bec5;
  float: left;
  margin-left: 10px;
  border-radius: 10px;
  height: 300px;
}
.list-group-item {
  margin: 10px;
  border: 3px solid blue;
  border-radius: 10px;
  padding: 5px 10px;
}
.list-group-item:hover {
  border: 2px solid red;
}
h2 {
  text-align: center;
}
button {
  color: white;
}
</style>
