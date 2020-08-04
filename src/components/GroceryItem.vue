<template>
<div>
  <div class="item" v-if="groceries.length === 0">Não há items na lista</div>
  <div 
    v-else
    v-for="(grocery, index) in groceries"
    class="item"
    @click="deleteGrocery(index)"
    :key="`${grocery.name}-${index}`">
    {{ grocery.name }}
  </div>
</div>
</template>

<script lang="ts">
import Vue from 'vue'
export default Vue.extend({
  props: {
    groceries: Array
  },
  methods: {
    deleteGrocery(index: number) {
      this.$emit('delete-grocery', index)
    }
  }
})
</script>