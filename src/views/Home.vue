<template>
  <div class="home">

    <MobileQuickLinks/>
    <ProductMarkets/>
    <MemberArea/>
    <QuickLinks/>
    <AppBanner/>

  </div>
</template>

<script>
// @ is an alias to /src
import MobileQuickLinks from '@/components/Home/MobileQuickLinks.vue';
import ProductMarkets from '@/components/Home/ProductMarkets.vue';
import MemberArea from '@/components/Home/MemberArea.vue';
import QuickLinks from '@/components/Home/QuickLinks.vue';
import AppBanner from '@/components/Home/AppBanner.vue';

export default {
  name: 'Home',

  components: {
    MobileQuickLinks,
    ProductMarkets,
    MemberArea,
    QuickLinks,
    AppBanner,
  },
};
</script>

<style lang="scss">
@import '@/styles/_variables.scss';

.home {
  background-color: $ltGray;
  padding: 20px 10px;
}  
</style>
