<template>
<header class="header">
  <h1>My multiselect App to train</h1>
</header>
<section class="list-section">
  <div class="ls-container">
    <template v-for="item in datas" :key="item.id">
      <ListItemComponent :item="item" />
    </template>
  </div>
</section>
</template>

<script setup lang="ts">

import ListItemComponent from '@/components/ListItemComponent.vue';
import datas from '@/datas/datas.json';
</script>

<style lang="scss" scoped>
  .header {
    width: 100%;
    height: 85px;
    background-color: rgb(78, 77, 77);
    justify-content: center;
    display: flex;
    align-items: center;

    h1 {
      margin: 0;
      text-align: center;
      color: rgb(224, 224, 253);
    }
  }

  .list-section {
    width: 100%;

    .ls-container {
      box-sizing: border-box;
      padding: 30px;
      border: 1px solid rgb(78, 77, 77);
      width: 100%;
      min-height: 400px;
      border-radius: 5px;
      max-width: 1200px;
      margin: 100px auto;

      .item-wrapper {
        margin: 25px;
      }
    }

  }
</style>