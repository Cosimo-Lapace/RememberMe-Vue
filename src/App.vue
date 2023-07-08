<template>
<the-header title="RememberMe"></the-header>
  <store-resource :resources="storeResources"></store-resource>
</template>

<script>
import TheHeader from './components/layouts/TheHeader.vue';
import StoreResources from './components/learning-resource/StoreResouces.vue';

export default {
  components: {
    'store-resource': StoreResources,
    'the-header': TheHeader,
  },

  data() {
    return {
      storeResources: [
        {
          id: '1',
          title: 'Official Guide',
          description: 'Vue.Js doc',
          link: 'https://vuejs.org/',
        },
        {
          id: '2',
          title: 'Official Guide2',
          description: 'Vue.Js doc2',
          link: 'https://vuejs.org/',
        },
      ],
    };
  },
};
</script>
<style>
@import url('https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap');

* {
  box-sizing: border-box;
}

html {
  font-family: 'Roboto', sans-serif;
}

body {
  margin: 0;
}
</style>
