<template>
  <ul>
    <learning-resource
      v-for="storeResource in storeResources"
      :key="storeResource.id"
      :title="storeResource.title"
      :description="storeResource.description"
      :link="storeResource.link"
    ></learning-resource>
  </ul>
</template>

<script>
import LearningResource from './components/learning-resource/LearningResource.vue';
export default {
  components: {
    'learning-resource': LearningResource,
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
