<template>
   <div class="list-item">
    <ListheaderComponent 
      :firstname="props.item.firstname"
      :lastname="props.item.lastname"
      :email="props.item.email"
      @checkAll="checkAllChildren"
    />
    <template v-for="child in props.item.children" :key="child.id">
      <ListChildComponent
        :child="child"
        :isChecked="isChecked"
      />
    </template>
  </div>
</template>

<script setup lang="ts">
  import { ref } from 'vue';
  import ListheaderComponent from "@/components/ListheaderComponent.vue";
  import ListChildComponent from "@/components/ListChildComponent.vue";

  const props = defineProps({
    item: {type: Object, required: true},
  })

  const isChecked = ref(false);

  const checkAllChildren = () => {
    isChecked.value = !isChecked.value;
}

</script>

<style lang="scss" scoped>
.list-item {
  width: 100%;
  margin: 50px 0;
  /* border-bottom: 1px solid rgb(78, 77, 77); */
  box-sizing: border-box;
}

</style>