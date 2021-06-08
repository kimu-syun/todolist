<template>
  <div>
    <h1>ItemList</h1>
    <div>
      <label>
        Item
        <input v-model="newItemName" type="text" />
      </label>
      <label>
        Place
        <input v-model="newItemPrice" type="number" />
      </label>
      <button @click="addItem">add</button>
    </div>
    <div v-for="item in items" :key="item.name">
      <div class="item" :class="{ over500: item.price >= 500}">
        <div>
          Item: {{ item.name }}  {{ item.price }} 円
        </div>
        <div v-if="item.price >= 10000">高額商品</div>
      </div>
    </div>
  </div>
</template>

<script>
import { ref } from "vue";

export default {
  setup() {
    const items = ref([
    ]);
    const newItemName = ref("");
    const newItemPrice = ref(0);

    const addItem = () => {
        if (newItemName.value != "") {
            items.value.push({ name: newItemName.value, price: newItemPrice.value });
        }
        newItemName.value = "";
        newItemPrice.value = 0;
    };
    return { items, newItemName, newItemPrice, addItem };
  },
};
</script>

<style>
.over500 {
    color: red;
}
</style>