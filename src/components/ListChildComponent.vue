<template>
   <div class="list-child">
    <input type="checkbox" :checked="props.isChecked">
    <h2>{{ props.child.firstname }} {{ props.child.lastname }}</h2>
  </div>
</template>

<script setup lang="ts">
import { onMounted, onUpdated } from "@vue/runtime-core"


const props = defineProps({
  child: { type: Object, required: true },
  isChecked: {type: Boolean}
})

onMounted(() => console.log('Monté'));

onUpdated(() => console.log('Updaté'))

</script>

<style lang="scss" scoped>
.list-child {
  display: flex;
  border-bottom: 1px solid rgb(78, 77, 77);
  box-sizing: border-box;
  padding: 0px 20px;

  &:last-child {
    border-bottom: none;
  }

  input {
    margin: 0 20px 0 0;
  }

}

</style>