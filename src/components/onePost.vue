<template lang="">
  <div>
    <h2 @click="show = !show">{{ post.title }}</h2>
    <p v-if="show">{{ extract }}</p>
  </div>
</template>
<script>
import { computed, onMounted, onUpdated, ref, onUnmounted } from 'vue';
export default {
  props: ['post'],
  setup(props) {
    const extract = computed(() => props.post.content.substring(0, 3) + '...');

    //life cycle hooks
    onMounted(() => {
      console.log('je suis entrer ');
    }),
      onUpdated(() => {
        console.log('je suis en modification');
      });
    onUnmounted(() => {
      console.log('je suis en sortie ');
    });
    const show = ref(true);
    return { extract, show };
  },
};
</script>
<style lang=""></style>
