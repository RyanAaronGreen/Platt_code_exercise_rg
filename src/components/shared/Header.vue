<template>
  <header>
      <div class="top">
          <a href="/" class="brand">
            <img class="brand__logo" :src="require('../../assets/logo.png')" alt="Platt Eletric Supply" >
          </a>

          <nav class="top__navigation">
            <ul class="top__navigation_list">
              <li class="top__navigation_list_item top__navigation_list_item--search">
                <button class="top__navigation__link" id="searchTrigger"><SearchIcon/> Search Trigger</button>
              </li>
              <li class="top__navigation_list_item top__navigation_list_item--cart">
                <a class="top__navigation__link" href="#"><CartIcon/> Cart</a>
              </li>
              <li class="top__navigation_list_item top__navigation_list_item--account">
                <a class="top__navigation__link" href="#"><AccountIcon/> Account</a>
              </li>
              <li class="top__navigation_list_item top__navigation_list_item--menu">
                <button class="top__navigation__link" id="menuTrigger"><MenuIcon/> Menu</button>
              </li>
            </ul>
          </nav>
      </div>

      <Search />
  </header>
</template>

<script>
// Components
import Search from '@/components/shared/SearchBar.vue';

// Icons
import SearchIcon from '@/assets/icons/ic_search.svg';
import AccountIcon from '@/assets/icons/ic_person.svg';
import CartIcon from '@/assets/icons/ic_cart.svg';
import MenuIcon from '@/assets/icons/ic_menu.svg';

export default {
  components: {
    Search,
    SearchIcon,
    AccountIcon,
    CartIcon,
    MenuIcon,
  },

};
</script>

<style lang="scss">
@import '@/styles/_variables.scss';

header {
  z-index: 3;
  position: relative;
  background-color: $plattGreen;
  padding: 10px;
}

.top {
  display: flex;
  justify-content: space-between;
  align-items: center;

  .brand {
    width: 145px;

    &--logo {
        max-width: 100%;
        width: 145px;
      }
  }

  .top__navigation {
    &__link {
      background: transparent;
      border: 0;
      cursor: pointer;

      svg {
        fill: #fff;
        height: 30px;
        width: 30px;
        transition: all 0.3s;
      }

      &:hover {
        svg {
          fill: #000;
        }
      }
    }

    &_list {
      list-style-type: none;
      padding: 0;
      margin: 0;

      &_item {
        display: inline-block;
        color: transparent;
        font-size: 0;
        position: relative;
        margin-left: 8px; 

        &--account {
          &:after {
            content:'';
            position: absolute;
            top: 0;
            right: 0;
            height: 5px;
            width: 5px;
            background-color: orange;
            border-radius: 100%;
            box-shadow: 0 2px 3px 2px rgba(0, 0, 0, 0.2);
          }
        }
      }
    }
  }
  
}

</style>
