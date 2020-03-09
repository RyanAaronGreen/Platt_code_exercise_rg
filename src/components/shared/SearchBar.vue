<template>
    <div class="search-bar">
      <form class="search-bar__form" action="">
        <label class="sr-only" for="search-bar">What are you looking for?</label>
        <vue-suggestion 
          :items="items" 
          v-model="item" 
          :setLabel="setLabel"
          :itemTemplate="searchTemplate"
          @changed="inputChange" 
          @selected="itemSelected"
          @enter="submitSearch"
          >
        </vue-suggestion>
        <button type="submit" @click="submitSearch" class="search-bar__submit">
            <SearchIcon/>
            <span class="sr-only">Search</span>
        </button>
      </form>
  </div>
</template>

<script>
import { VueSuggestion } from 'vue-suggestion';
import axios from 'axios';
import VueAxios from 'vue-axios';

import searchTemplate from '@/components/shared/SearchTemplate.vue';

// Icons
import SearchIcon from '@/assets/icons/ic_search.svg';


const apiEndpoint = 'https://dog.ceo/api/breeds/list/all';

export default {
  name: 'Search',
  data() {
    return {
      item: {},
      items: [],
      allItems: [],
      searchTemplate,
    };
  },
  methods: {
    itemSelected(item) {
      this.item = item;
    },
    submitSearch() {
      // eslint-disable-next-line 
      alert(`Searching for ${this.item[0]}`);
    },
    setLabel(item) {
      return item[0];
    },
    inputChange(text) {
      const searchedItems = this.allItems.filter(item => new RegExp(text.toLowerCase()).test(item[0].toLowerCase()));
      if (searchedItems.length === 0) {
        this.items = { 0: text };
        this.item = { 0: text };
      } else {
        this.items = searchedItems;
      } 
    },
  },
  mounted() {
    axios.get(apiEndpoint)
      .then((response) => {
        // Change object response into an array for vue-suggestion
        const responseAsArray = Object.keys(response.data.message).map((key) => [key, response.data.message[key]]);
        this.allItems = responseAsArray;
      });
  },
    
  components: {
    VueSuggestion,
    SearchIcon,
  },
};
</script>

<style lang="scss">
@import '@/styles/_variables.scss';
.search-bar__form {
  height: 100%;
  width: 100%;
}
.vue-suggestion {
  height: 100%;
  width: 100%;
}
.vs__input-group {
  height: 100%;
  width: 100%;
}
.vue-suggestion .vs__list {
    width: 100%;
    text-align: left;
    border: none;
    border-top: none;
    max-height: 400px;
    overflow-y: auto;
    border-bottom: 1px solid $plattGreen;
    position: relative;
}
.vue-suggestion .vs__list .vs__list-item {
    background-color: #fff;
    padding: 10px;
    border-left: 1px solid $plattGreen;
    border-right: 1px solid $plattGreen;
}
.vue-suggestion .vs__list .vs__list-item:last-child {
    border-bottom: none;
}
.vue-suggestion .vs__list .vs__list-item:hover {
    background-color: #eee !important;
}
.vue-suggestion .vs__list,
.vue-suggestion .vs__loading {
    position: absolute;
}
.vue-suggestion .vs__list .vs__list-item {
    cursor: pointer;
}
.vue-suggestion .vs__list .vs__list-item.vs__item-active {
    background-color: #8a9199;
}

.search-bar {
    position: relative;
    display: block;
    height: 45px;
    margin: 10px 20px;
    box-sizing: border-box;

    &__input ,
    .vs__input {
        width: 100%;
        height: 100%;
        border-radius: 5px;
        border: 0;
        margin: 0;
        padding: 0 65px 0 20px;
        box-sizing: border-box;
    }
    &__submit {
        position: absolute;
        top: 0;
        right: 0;
        height: 100%;
        width: 45px;
        line-height: 45px;
        background: 0;
        border: 0;
        vertical-align: middle;
        text-align: center;
        svg {
            display: block;
            margin: 0 auto;
        }
    }
    
    .autocomplete-results {
      padding: 0;
      margin: 0;
      border: 1px solid #eeeeee;
      height: 120px;
      overflow: auto;
    }

    .autocomplete-result {
      list-style: none;
      text-align: left;
      padding: 4px 2px;
      cursor: pointer;
    }

    .autocomplete-result:hover {
      background-color: #4AAE9B;
      color: white;
    }
}

</style>
