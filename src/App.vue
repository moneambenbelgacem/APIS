<template>
  <div id="nav">
    <router-link to="/">Home</router-link> |
    <router-link to="/blog">Blog</router-link> |
    <router-link to="/about">About</router-link>
  </div>
  <router-view />
  <div>
    <button @click="preview">PREVIEW</button>
    <button @click="next">NEXT</button>
    <button @click="redirect">BACK TO HOME</button>
  </div>
</template>
<script>
import { useRouter } from 'vue-router';
export default {
  setup() {
    const router = useRouter();
    const preview = () => {
      router.go(-1);
    };
    const next = () => {
      router.go(1);
    };
    const redirect = () => {
      router.push('/');
    };
    return { preview, next, redirect };
  },
};
</script>
<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}
</style>
