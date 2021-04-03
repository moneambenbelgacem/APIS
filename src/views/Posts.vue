<template lang="">
  <h1>List of posts</h1>
  <label for="cherche">chercher un post</label>
  <input v-model="search" id="cherche" type="text" />
  <div v-for="post in result" :key="post.id">
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
      { id: 15, title: 'Rank', slug: 'Solarbreeze', content: 'Integra' },
      {
        id: 16,
        title: 'Treeflex',
        slug: 'Voltsillam',
        content: 'E-350 Super Duty Van',
      },
      { id: 17, title: 'Ventosanzap', slug: 'Voltsillam', content: 'MX-6' },
      { id: 18, title: 'Home Ing', slug: 'Voltsillam', content: 'Forester' },
      { id: 19, title: 'Zontrax', slug: 'Tres-Zap', content: 'Tundra' },
      { id: 20, title: 'Transcof', slug: 'Biodex', content: 'Eldorado' },
      { id: 21, title: 'Fix San', slug: 'Stringtough', content: 'Camry' },
      { id: 22, title: 'Voltsillam', slug: 'Tin', content: 'E-Class' },
      { id: 23, title: 'Treeflex', slug: 'Bamity', content: 'Gallardo' },
      { id: 24, title: 'Temp', slug: 'Ronstring', content: 'Swift' },
      { id: 25, title: 'Bytecard', slug: 'Viva', content: 'Mirage' },
      {
        id: 26,
        title: 'Y-find',
        slug: 'Prodder',
        content: 'LTD Crown Victoria',
      },
      { id: 27, title: 'Overhold', slug: 'Tresom', content: 'E-Class' },
      { id: 28, title: 'Temp', slug: 'Sonsing', content: 'Fairlane' },
      { id: 29, title: 'Andalax', slug: 'Zamit', content: '6 Series' },
      { id: 30, title: 'Alpha', slug: 'Aerified', content: 'Blazer' },
      { id: 31, title: 'Home Ing', slug: 'Keylex', content: 'Continental' },
      { id: 32, title: 'Bigtax', slug: 'Prodder', content: 'Sorento' },
      { id: 33, title: 'Fix San', slug: 'Voltsillam', content: 'Electra' },
      { id: 34, title: 'Rank', slug: 'Home Ing', content: 'Accent' },
      { id: 35, title: 'Biodex', slug: 'Matsoft', content: 'SJ' },
      { id: 36, title: 'Aerified', slug: 'Y-Solowarm', content: 'W201' },
      { id: 37, title: 'Keylex', slug: 'Overhold', content: 'M-Class' },
      { id: 38, title: 'Y-find', slug: 'Konklab', content: 'Tacoma' },
      { id: 39, title: 'Matsoft', slug: 'Bitchip', content: 'Crown Victoria' },
      { id: 40, title: 'Cardify', slug: 'Home Ing', content: 'Pajero' },
      { id: 41, title: 'Tresom', slug: 'Zoolab', content: 'GTO' },
      { id: 42, title: 'Cardguard', slug: 'Zamit', content: '1 Series' },
      { id: 43, title: 'Cardify', slug: 'It', content: 'MX-3' },
      { id: 44, title: 'Span', slug: 'Trippledex', content: 'E150' },
      { id: 45, title: 'Bytecard', slug: 'Span', content: 'Echo' },
      { id: 46, title: 'Namfix', slug: 'Sub-Ex', content: 'Club Wagon' },
      { id: 47, title: 'Trippledex', slug: 'Redhold', content: 'V8 Vantage' },
      { id: 48, title: 'Cookley', slug: 'Stim', content: 'Express 1500' },
      {
        id: 49,
        title: 'Trippledex',
        slug: 'Keylex',
        content: 'Town & Country',
      },
      { id: 50, title: 'Asoka', slug: 'Prodder', content: 'Compass' },
      { id: 51, title: 'Flexidy', slug: 'Y-Solowarm', content: 'Probe' },
      { id: 52, title: 'Sonair', slug: 'Temp', content: 'FX' },
      { id: 53, title: 'Home Ing', slug: 'Tin', content: 'Titan' },
      { id: 54, title: 'Subin', slug: 'Zathin', content: 'Windstar' },
      { id: 55, title: 'Biodex', slug: 'It', content: 'Ram 3500' },
      { id: 56, title: 'Gembucket', slug: 'Zontrax', content: 'F150' },
      { id: 57, title: 'Biodex', slug: 'Asoka', content: 'Suburban 1500' },
      { id: 58, title: 'Flowdesk', slug: 'Matsoft', content: 'E250' },
      { id: 59, title: 'Flowdesk', slug: 'Job', content: 'Civic' },
      { id: 60, title: 'Bigtax', slug: 'Andalax', content: 'Camaro' },
      { id: 61, title: 'Pannier', slug: 'Y-Solowarm', content: 'Stratus' },
      { id: 62, title: 'Sub-Ex', slug: 'Span', content: 'New Beetle' },
      { id: 63, title: 'Sonsing', slug: 'Bigtax', content: 'Odyssey' },
      {
        id: 64,
        title: 'Voltsillam',
        slug: 'Cookley',
        content: 'Econoline E250',
      },
      { id: 65, title: 'Job', slug: 'Duobam', content: 'Impreza' },
      { id: 66, title: 'Lotstring', slug: 'Alphazap', content: 'Discovery' },
      {
        id: 67,
        title: 'Trippledex',
        slug: 'Alphazap',
        content: 'Silverado 2500',
      },
      { id: 68, title: 'Asoka', slug: 'Job', content: 'Swift' },
      { id: 69, title: 'Zontrax', slug: 'Matsoft', content: 'Mazda3' },
      { id: 70, title: 'Flowdesk', slug: 'Konklab', content: 'Mazdaspeed6' },
      { id: 71, title: 'Otcom', slug: 'Transcof', content: 'Viper' },
      { id: 72, title: 'Stim', slug: 'Fixflex', content: 'LS Hybrid' },
      { id: 73, title: 'Cookley', slug: 'Daltfresh', content: 'RAV4' },
      {
        id: 74,
        title: 'Flexidy',
        slug: 'Stronghold',
        content: 'Yukon XL 2500',
      },
      { id: 75, title: 'Wrapsafe', slug: 'Solarbreeze', content: 'J' },
      { id: 76, title: 'Treeflex', slug: 'Cardify', content: '164' },
      { id: 77, title: 'Opela', slug: 'Stim', content: 'Sunfire' },
      { id: 78, title: 'Veribet', slug: 'Voltsillam', content: 'D150 Club' },
      { id: 79, title: 'Fixflex', slug: 'Voltsillam', content: 'Diamante' },
      { id: 80, title: 'Zoolab', slug: 'Aerified', content: 'Liberty' },
      { id: 81, title: 'Zaam-Dox', slug: 'Job', content: 'Journey' },
      { id: 82, title: 'Zamit', slug: 'Bigtax', content: 'D350 Club' },
      { id: 83, title: 'Duobam', slug: 'Mat Lam Tam', content: 'Yukon' },
      { id: 84, title: 'It', slug: 'Tresom', content: 'D350' },
      { id: 85, title: 'Trippledex', slug: 'Y-find', content: 'Discovery' },
      { id: 86, title: 'Otcom', slug: 'Stim', content: 'E-Class' },
      { id: 87, title: 'Subin', slug: 'Daltfresh', content: 'Thunderbird' },
      { id: 88, title: 'Konklab', slug: 'Flexidy', content: 'Miata MX-5' },
    ]);
    const search = ref('');
    const result = computed(() => {
      return posts.value.filter((post) => post.title.includes(search.value));
    });
    return { posts, result, search };
  },
};
</script>
<style lang=""></style>
