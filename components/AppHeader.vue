<template lang="html">
  <header class="header">
    <nuxt-link to="/"><h1 class="title">Dad Jokes</h1></nuxt-link>
    <ul>
      <li> <nuxt-link to="/">HOME</nuxt-link> </li>|
      <li> <nuxt-link to="/about">ABOUT US</nuxt-link> </li>|
      <li> <nuxt-link to="/jokes">JOKES</nuxt-link> </li>
    </ul>
  </header>
</template>

<script>
export default {
  name: 'AppHeader'
}
</script>

<style lang="css" scoped>
.header{
  display: flex;
}
.header ul{
  flex-grow: 1;
  display: flex;
  justify-content: space-evenly;
  align-items: center;
}
.header ul li{
  list-style: none;
}
.header ul li a{
  text-decoration: none;
}
.title{
  font-size: 1.6rem;
  font-weight: normal;
}

</style>
