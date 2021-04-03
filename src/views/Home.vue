<template>
  <div class="home">
    <h1 ref="titre">this is home page</h1>
    <p>
      my name is :{{ myname }} <br />
      et mon ecole est : {{ monecole }} <br />
      et mon age : {{ myage }}
    </p>
    <h2>{{ person1.name }}</h2>
    <h2>{{ person2.name }}</h2>
    <button @click="sayhello">marhaba</button>
    <button @click="myage++">Inc</button>
  </div>
</template>

<script>
// @ is an alias to /src
import { ref, reactive } from 'vue';
export default {
  name: 'Home',
  setup() {
    let name = ref('moneam');
    let ecole = ref('ESEN');
    let age = ref(24);
    let titre = ref(null);
    let person1 = ref({ name: 'marwan', dest: 'canada' });
    let person2 = reactive({ name: 'karim', age: 55 });

    const sayhello = () => {
      console.log(titre.value);
      titre.value.classList.add('my-2');
      name.value = 'heloo every time ';
      person1.value.name = 'mahrez';
      person2.name = 'malek';
    };

    return {
      myname: name,
      monecole: ecole,
      sayhello,
      titre,
      myage: age,
      person1,
      person2,
    };
  },
};
</script>
