<template>
  <base-card>
    <base-button @click='setSelectedTab("stored-resources")' :mode="storedResButtonMode">Stored Resources</base-button>
    <base-button  @click='setSelectedTab("add-resource")' :mode="addResButtonMode">Add Resource</base-button>
  </base-card>
  <keep-alive>
  <component :is="selectedTab">
  </component>
  </keep-alive>
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
  computed: {
    storedResButtonMode() {
    return this.selectedTab ==='stored-resources' ? null : 'flat'
    },
    addResButtonMode() {
      return this.selectedTab ==='add-resource' ? null : 'flat'
    }
  },
  provide() {
    return{
      resources: this.storedResources,
      addResource: this.addResource,
      removeResource: this.removeResource
    }
  },
  methods: {
    setSelectedTab(tab) {
      this.selectedTab=tab;
    },
    addResource(title, desc, url) {
      const newResource = {
        id: new Date().toISOString(),
        title:title,
        description:desc,
        link:url,
      };
      this.storedResources.unshift(newResource);
      this.selectedTab = 'stored-resources';
    },
    removeResource(resId) {
      const resIndex = this.storedResources.findIndex (res => res.id === resId);
      this.storedResources.splice(resIndex, 1);
    }
  },
}
</script>
