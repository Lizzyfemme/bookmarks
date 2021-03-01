<template>
  <ul>
  </ul>
</template>

<script>
export default {
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