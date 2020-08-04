<template>
  <div class="container">
    <input type="text" v-model="groceryName">
    <button @click="sendItem" style="margin-left: 8px;">Send</button>
    <h1>Groceries List</h1>
    <div class="card">
      <GroceryItem :groceries="groceries" @delete-grocery="onDeleteGrocery"/>
    </div>
  </div>
</template>
<style>
  .container {
    width: 350px;
    margin:0 auto;
  }
  .card {
    padding: 16px;
    border-radius: 4px;
    border: 1px solid #d3d3d3;
  }
  .item {
    border: 1px solid #AAA;
    border-radius: 4px;
    padding: 8px;
    margin-bottom: 8px;
  }
</style>
<script lang="ts">
import Vue from 'vue'
import GroceryItem from '@/components/GroceryItem.vue'

export default Vue.extend({
  name: 'GroceriesList',
  components: {
    GroceryItem
  },
  data() {
    return {
      groceries: [
        {
          name: 'Bolacha',
        }
      ],
      groceryName: ''
    }
  },
  methods: {
    sendItem() {
      this.groceries.push({ name: this.groceryName })
    },
    onDeleteGrocery(index: number) {
      this.groceries.splice(index, 1)
    }
  }
})
</script>