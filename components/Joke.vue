<template lang="html">
  <nuxt-link :to="'jokes/' + id">
    <div class="joke">
      <p>{{ joke }}</p>
    </div>
  </nuxt-link>
</template>

<script>
export default {
  name: 'Joke',
  props: ['joke', 'id']
}
</script>

<style lang="css" scoped>
.joke{
  padding: 1rem;
  border: 1px dotted #ccc;
  margin: 1rem 0 0;
}
</style>
