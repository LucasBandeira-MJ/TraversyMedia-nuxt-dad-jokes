<template lang="html">
  <div>
    {{ $route.params.id }}
  </div>
</template>

<script>
import axios from 'axios';

export default {
  data(){
    return{
      joke:{}
    }
  },
  async created(){
    const config = {
      headers: { 'Accept': 'application/json' }
    }
    try {
      const res = await axios.get(`https://icanhazdadjoke.com/j/0189hNRf2g`, config);

      this.joke = res.data;
      console.log(this.joke)
    } catch (e) {
      console.log(e);
    }
  }
}
</script>

<style lang="css" scoped>
</style>
