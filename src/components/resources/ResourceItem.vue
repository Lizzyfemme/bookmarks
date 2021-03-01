<template>
  <li>
    <header>
      <h3>{{ title }}</h3>
      <button>Delete</button>
    </header>
    <p>{{ description }}</p>
    <a :href='link'></a>
  </li>
</template>
<script>
export default {
  props: [
    'title', 'description', 'link'
  ]
}
</script>