<template>
    <section class="mobile_quick_links">
        <a href="#" class="quick_link">
          <div class="icon_wrapper">
            <CategoryIcon/>
          </div>
          Categories
        </a>
        <a href="#" class="quick_link">
          <div class="icon_wrapper">
            <SearchIcon/>
          </div>
          Search
        </a>
        <a href="#" class="quick_link">
          <div class="icon_wrapper">
            <ScannerIcon/>
          </div>
          Scan
        </a>

    </section>
</template>

<script>
import SearchIcon from '@/assets/icons/ic_search.svg';
import CategoryIcon from '@/assets/icons/ic_line_style.svg';
import ScannerIcon from '@/assets/icons/ic_scanner.svg';

export default {
  
  components: {
    ScannerIcon,
    CategoryIcon,
    SearchIcon,
  },

};
</script>

<style lang="scss">
@import '@/styles/_variables.scss';

.mobile_quick_links {
  padding: 0px 0 20px;
  display: flex;
  align-items: center;
  justify-content: center;
    .quick_link {
      color: #000;
      text-decoration: none;
    }
    .icon_wrapper {
      background-color: #fff;
      display: flex;
      align-items: center;
      justify-content: center;
      margin: 0 10px 10px;
      border-radius: 100%;
      padding: 15px;
      box-shadow: $shadow;
    }
    svg {
      height: 50px;
      width: 50px;
    }

  @media(min-width: $tablet) {
    display: none;
  } 
}
</style>
