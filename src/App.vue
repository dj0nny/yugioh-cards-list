<template>
  <div class="app__content">
    <h1 class="app__name">Yu-Gi-Oh Cards List</h1>
    <Search :handleSearch="handleSearch" />
    <Card :card="cardData.data" v-if="cardData.data" />
    <div class="error" v-else>
      {{cardData.error}}
    </div>
  </div>
</template>

<script>
import { ref } from 'vue';
import Search from './components/Search';
import Card from './components/Card';

import API from './API';

export default {
  name: 'App',
  components: {
    Search,
    Card
  },
  setup() {
    const cardData = ref({});

    const handleSearch = async (card) => {
      cardData.value = await (await fetch(`${API.BASE_URL}?name=${card}`)).json();
    }

    return {
      handleSearch,
      cardData,
    }
  },
}
</script>

<style>
</style>
