<template lang="">
  <div>
    <h2>{{ post.title }}</h2>
    <p>{{ extract }}</p>
  </div>
</template>
<script>
import { computed } from 'vue';
export default {
  props: ['post'],
  setup(props) {
    const extract = computed(() => props.post.content.substring(0, 3) + '...');

    return { extract };
  },
};
</script>
<style lang=""></style>
