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

<style scoped>
  ul {
    list-style-type: none;
    text-align: center;
    margin-top: 0;
  }
  li {
   display: center;
   min-height: 50px;
   height: 50px;
   line-height: 50px;
   margin: 0.5rem 0;
   padding: 0 0.9rem;
   background: white;
   border-radius: 5px;
   text-align: center;
  }

</style>
