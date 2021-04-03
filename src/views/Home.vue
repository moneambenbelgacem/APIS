<template>
  <div class="home">
    <h1 ref="titre">this is home page</h1>
    <p>
      my name is :{{ myname }} <br />
      et mon ecole est : {{ monecole }} <br />
      et mon age : {{ myage }}
    </p>
    <button @click="sayhello">marhaba</button>
    <button @click="myage++">Inc</button>
  </div>
</template>

<script>
// @ is an alias to /src
import { ref } from 'vue';
export default {
  name: 'Home',
  setup() {
    let name = ref('moneam');
    let ecole = ref('ESEN');
    let age = ref(24);
    let titre = ref(null);

    const sayhello = () => {
      console.log(titre.value);
      titre.value.classList.add('my-2');
      name.value = 'heloo every time ';
    };

    return {
      myname: name,
      monecole: ecole,
      sayhello,
      titre,
      myage: age,
    };
  },
};
</script>
