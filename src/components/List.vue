<template>
  <section>
    <ul>
      <li v-for="(todoItem, index) in propsdata">{{ todoItem }}</li>
    </ul>
  </section>
</template>

<script>
export default {
  props: ['propsdata'],
  }
</script>
