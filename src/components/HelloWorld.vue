<template>
  <div>
    <h1>{{ msg }}</h1>
    <dev class="cmp">
      <counter />
      <item-list/>
      <todolist/>
    </dev>
  </div>
</template>

<script>
import Counter from "./Counter.vue";
import ItemList from "./ItemList.vue";
import Todolist from './Todolist.vue';

export default {
  components: {
    Counter,
    ItemList,
    Todolist,
  },
  props: {
    msg: {
      type: String,
      default: "",
    },
  },
};
</script>

<style scoped>
a {
  color: #42b983;
}
.cmp{
  display: flex;
  justify-content: space-evenly;
}
</style>
