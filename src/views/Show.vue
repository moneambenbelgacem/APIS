<template lang="">
  <div>
    <h2>mon composant show</h2>
  </div>
</template>
<script>
import { useRoute } from 'vue-router';
export default {
  setup() {
    const route = useRoute();

    console.log(route.params.id);
  },
};
</script>
<style lang=""></style>
