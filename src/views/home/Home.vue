<template>
  <div class="home">

    <nav-bar class="home-nav">
      <div slot="center">购物街</div>
    </nav-bar> 

    <home-swiper :banners="banners" />
    <recommend-view :recommends="recommends" />
    <feature-view/>
    <tab-control :titles="titles" />

    <ul>
      <li>1</li>
      <li>2</li>
      <li>3</li>
      <li>4</li>
      <li>5</li>
      <li>6</li>
      <li>7</li>
      <li>8</li>
      <li>9</li>
      <li>10</li>
      <li>11</li>
      <li>12</li>
      <li>13</li>
      <li>14</li>
      <li>15</li>
      <li>16</li>
      <li>17</li>
      <li>18</li>
      <li>19</li>
      <li>20</li>
    </ul>

  </div>
</template>

<script>
import HomeSwiper from './childComp/HomeSwiper'
import RecommendView from './childComp/RecommendView'
import FeatureView from './childComp/FeatureView'

import NavBar from 'components/common/navbar/NavBar'
import TabControl from 'components/content/tabControl/TabControl'

import {getHomeMultidata} from 'network/home'
export default {
  name: 'Home',
  data() {
    return {
      // 轮播图图片
      banners: [],
      recommends: [],
      titles: ['流行','新款','精选']
    }
  },
  created() {
    getHomeMultidata().then(res => {
      console.log(res)
      this.banners = res.data.banner.list
      this.recommends = res.data.recommend.list
    })
  },
  components: {
    HomeSwiper,
    RecommendView,
    FeatureView,
    NavBar,
    TabControl,
  }
}
</script>

<style scoped>
  .home-nav {
    background-color: var(--color-tint);
    color: #fff;
  }
</style>
