<template>
  <ul>
    <resource-item v-for="res in storedResources" 
    :key="res.id" 
    :title='res.title'
    :description="res.description"
    :link="res.link"
    >
    </resource-item> 
  </ul>
</template>

<script>
import ResourceItem from './components/resources/ResourceItem'
export default {
  components: {
    ResourceItem,
  },
  data() {
    return {
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
    }
  }
}
</script>