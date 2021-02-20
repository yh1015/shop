<template>
  <div class="home">

    <nav-bar class="home-nav">
      <div slot="center">购物街</div>
    </nav-bar> 

  </div>
</template>

<script>
import NavBar from 'components/common/navbar/NavBar'
import {getHomeMultidata} from 'network/home'
export default {
  name: 'Home',
  components: {
    NavBar
  }
}
</script>

<style scoped>
  .home-nav {
    background-color: var(--color-tint);
    color: #fff;
  }
</style>
