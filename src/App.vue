
<template>
  <div id="app">
    <vHeader />
    <CategoryList />
    <router-view/>
    <vFooter />
  </div>
</template>

<script>
import vHeader from '@/components/shared/Header.vue';
import CategoryList from '@/components/shared/CategoryList.vue';
import vFooter from '@/components/shared/Footer.vue';

export default {
  components: {
    vHeader,
    CategoryList,
    vFooter,
  },
};
</script>

<style lang="scss">
@import '@/styles/_main.scss';
@import '@/styles/_variables.scss';

#app {
  font-family: $ptSans;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
img {
  max-width: 100%;
  height: auto;
}

</style>
