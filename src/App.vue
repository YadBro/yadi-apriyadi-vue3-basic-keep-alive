<template>
  <h1 class="text-center mt-5">Belajar Vue | Yadi Apriyadi</h1>
  <div class="d-flex justify-content-center flex-column align-items-center mt-4">
    <div>
    <b-button :variant="currentTab === tab ? 'success' : 'primary'"
      v-for="(tab, index) in tabs"
      :key="index" class="mx-1"
      @click="currentTab = tab">
      {{tab}}
    </b-button>
    </div>
    <div>
      <keep-alive>
        <component class="mt-2" :is="currentTabComponent" />
      </keep-alive>
    </div>
  </div>

</template>

<script>
import Home from './components/Home.vue';
import Post from './components/Post.vue';
import About from './components/About.vue';

export default {
  components: {Home, Post, About},
  data() {
    return {
      currentTab: "Home",
      tabs: ['Home', 'Post', 'About'],
    }
  },
  computed: {
    currentTabComponent() {
      return this.currentTab.toLowerCase();
    }
  }
}
</script>

<style>
  .active {
    color: green;
  }
</style>