<template lang="html">
  <div class="container joke-box">
    <Joke v-for="joke in jokes" :key="joke.id"
    :id="joke.id" :joke="joke.joke"/>
  </div>
</template>

<script>
import axios from 'axios';
import Joke from '~/components/Joke';

export default {
  components: {
    Joke
  },
  data(){
    return{
      jokes:[]
    }
  },
  async created(){
    const config = {
      headers: { 'Accept': 'application/json' }
    }
    try {
      const res = await axios.get('https://icanhazdadjoke.com/search', config);

      this.jokes = res.data.results;
      console.log(res.data);
    } catch (e) {
      console.log(e);
    }
  },
  head(){
    return{
      title: 'Dad joke',
      meta: [
        {
          hid: 'description',
          name: 'description',
          content: 'Best place for a quick not laugh'
        }
      ]
    }
  }
}
</script>

<style lang="css" scoped>
.joke-box{
  flex-direction: column;
}
</style>
