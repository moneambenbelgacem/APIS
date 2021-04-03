<template>
  <div class="home">
    <h1 ref="titre">this is home page</h1>
    <p>
      my name is :{{ myname }} <br />
      et mon ecole est : {{ monecole }}
    </p>
    <button @click="sayhello">marhaba</button>
  </div>
</template>

<script>
// @ is an alias to /src
import { ref } from 'vue';
export default {
  name: 'Home',
  setup() {
    let name = 'moneam';
    let ecole = 'ESEN';
    let titre = ref(null);

    const sayhello = () => {
      console.log(titre.value);
      titre.value.classList.add('my-4');
      titre.value.textContent = 'welcome to my web site';
    };

    return {
      myname: name,
      monecole: ecole,
      sayhello,
      titre,
    };
  },
};
</script>
