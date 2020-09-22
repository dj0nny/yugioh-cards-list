<template>
  <form class="searchForm" @submit.prevent="handleSubmit">
    <label for="cardName">Enter the card name</label>
    <input type="text" id="cardName" v-model="cardName" />
    <button type="submit">Search</button>
  </form>
</template>

<script>
import { ref } from 'vue';

export default {
  name: 'Search',
  props: {
    handleSearch: Function,
  },
  setup(props) {
    const cardName = ref('');

    const handleSubmit = () => {
      props.handleSearch(cardName.value);
    };

    return {
      cardName,
      handleSubmit,
    };
  },
}
</script>
