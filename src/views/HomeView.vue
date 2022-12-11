<template>
  <calculator />
</template>

<script>
import { defineComponent } from 'vue';

// Components
import calculator from '../components/calculator.vue';

export default defineComponent({
  name: 'HomeView',

  components: {
    calculator,
  },
});
</script>
