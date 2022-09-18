<template>
  <div class="list-header">
    <input type="checkbox" @click="$emit('checkAll')">
    <h2>{{ props.firstname }} {{ props.lastname }}</h2>
    <p>{{ props.email }}</p>
  </div>
</template>

<script setup lang="ts">

const props = defineProps({
  firstname: {type: String, required: true},
  lastname: {type: String, required: true},
  email: {type: String, required: true}
})

const emit = defineEmits(['checkAll']);

</script>

<style lang="scss" scoped>
  .list-header {
    display: flex;
    align-items: center;
    justify-content: space-between;
    background-color: rgb(165, 165, 253);
    box-sizing: border-box;
    padding: 5px 20px;
    border-radius: 5px 5px 0 0;
  }
</style>