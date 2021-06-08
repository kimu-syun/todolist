<template>
  <div>
    <h1>TodoList</h1>
    <div>
      <label>
        Task
        <input v-model="NewTasksname" type="text" />
      </label>
      <lebel>
          Limit
          <input v-model="Limittime" type="text" />
      </lebel>
      <button @click="addTask">add</button>
    </div>
    <div v-for="task in tasks" :key="task.name">
        <lebel v-bind:class="{ done: task.isChecked}">
            <input type="checkbox" v-model="task.isChecked"> {{task.name}}　期限：{{task.time}}
        </lebel>
    </div>
  </div>
</template>

<script>
import { ref } from "vue";

export default {
  setup() {
    const tasks = ref([
    ]);
    const NewTasksname = ref("");
    const Limittime = ref("")

    const addTask = () => {
        if (NewTasksname.value != "") {
         tasks.value.push({ name: NewTasksname.value, time: Limittime.value, isChecked: false});
        }
        NewTasksname.value = "";
        Limittime.value = "";
    };

    return { tasks, NewTasksname, Limittime, addTask };
  },

};
</script>

<style>
.done { text-decoration: line-through;}
</style>