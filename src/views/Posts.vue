<template lang="">
  <h1>List of posts</h1>
  <label for="cherche"></label>
  <input ref="search" id="cherche" type="text" />
  <div v-for="post in posts" :key="post.id">
    <onePost :post="post" />
  </div>
</template>
<script>
import { ref, computed } from 'vue';
import onePost from '../components/onePost';
export default {
  components: {
    onePost,
  },
  setup() {
    const posts = ref([
      { id: 5, title: 'Stim', slug: 'Tres-Zap', content: 'X5' },
      { id: 6, title: 'Opela', slug: 'Alphazap', content: 'Journey' },
      { id: 7, title: 'Cardguard', slug: 'Toughjoyfax', content: 'Fifth Ave' },
      { id: 8, title: 'Daltfresh', slug: 'Sonsing', content: 'Park Avenue' },
      { id: 9, title: 'Gembucket', slug: 'Flexidy', content: 'Ram Wagon B250' },
      { id: 10, title: 'Hatity', slug: 'Zathin', content: 'DBS' },
      { id: 11, title: 'Subin', slug: 'Bitchip', content: 'Electra' },
      { id: 12, title: 'Stronghold', slug: 'Aerified', content: 'Uplander' },
      { id: 13, title: 'Fixflex', slug: 'Stronghold', content: 'MPV' },
      { id: 14, title: 'Trippledex', slug: 'Holdlamis', content: 'Rendezvous' },
    ]);
    const search = ref('');
    const result = computed(() => {
      return posts.value.filter((post) => post.includes(search.value));
    });
    return { posts };
  },
};
</script>
<style lang=""></style>
