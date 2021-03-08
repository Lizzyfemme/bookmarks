<template>
  <base-card>
    <base-button @click='setSelectedTab("stored-resources")'>Stored Resources</base-button>
    <base-button  @click='setSelectedTab("add-resource")'>Add Resource</base-button>
  </base-card>
  <component :is="selectedTab">
  </component>
</template>

<script>
import StoredResources from "./StoredResources"
import AddResource from "./AddResource"
export default {
 
  components: {
    StoredResources,
    AddResource
  },
  data() {
    return{
      selectedTab: 'stored-resources',
       storedResources: [
        { 
          id: 'offical-guide', 
          title: 'Offical Guide',
          description: 'The offical Vue.js documentation',
          link: "https://vuejs.org"  
        },
        {
          id: 'google', 
          title: 'Google',
          description: 'The offical guide to anything',
          link: "https://google.com"  
        }
      ]
    };
  },
  provide() {
    return{
      resources: this.storedResources
    }
  },
  methods: {
    setSelectedTab(tab) {
      this.selectedTab=tab;
    }
  }
}
</script>