<template>
  <base-card>
    <base-button @click="setSelectedTab('store-resources')" :mode="storedResButtonMode"
      >Stored Resources</base-button
    >
    <base-button @click="setSelectedTab('add-resources')" :mode="addResButtonMode"
      >Add Resource</base-button
    >
  
  </base-card>
  <keep-alive>
    <component :is="selectedTab">
    
  </component>
  </keep-alive>
</template>

<script>
import AddResourcesVue from './AddResources.vue';
import StoreResources from './StoreResouces.vue';

export default {
  components: {
    'store-resources': StoreResources,
    'add-resources': AddResourcesVue,
  },
  data() {
    return {
      selectedTab: 'stored-resources',
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
  provide(){
    return{
        resources: this.storeResources,
        addRes: this.addResource,
    }
  },
  computed:{
    storedResButtonMode(){
        return this.selectedTab === 'store-resources' ? null : 'flat'
    },
    addResButtonMode(){
        return this.selectedTab === 'add-resources' ? null : 'flat'
    },
  },
  methods: {
    setSelectedTab(input) {
      this.selectedTab = input;
    },
    addResource(title,desc,link){
        const newResource = {
            id: new Date().toISOString,
            title: title,
            description: desc,
            link:link,
        }
        this.storeResources.unshift(newResource);
        this.selectedTab = 'store-resources';
    },
  },
};
</script>
