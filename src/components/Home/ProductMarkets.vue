<template>
    <section class="product-markets">
      <h2 class="product-markets__heading">Product Markets</h2>
      <div class="product-markets__cards">
        <a v-for="market in productMarkets" v-bind:key="market.name + market.id" :href="market.url" class="card">
          <div class="card__image" :style="{ 'background-image': `url(${market.image })` }"></div>
          <div class="card__content">
            <p>{{ market.name }}</p>
          </div>
        </a>
      </div>
    </section>
</template>

<script>
export default {
  data() {
    return {
      productMarkets: [
        { 
          id: 1,
          name: 'DataComm',
          url: '#',
          image: require('@/assets/images/datacomm-market.jpg'),
        },
        {
          id: 2,
          name: 'HVAC',
          url: '#',
          image: require('@/assets/images/hvac-market.jpg'),
        },
        {
          id: 3,
          name: 'Industrial',
          url: '#',
          image: require('@/assets/images/industrial-market.jpg'),
        },
        {
          id: 4,
          name: 'Lighting',
          url: '#',
          image: require('@/assets/images/lighting-market.jpg'),
        },
        {
          id: 5,
          name: 'Energy Efficiency',
          url: '#',
          image: require('@/assets/images/energy-efficiency-market.jpg'),
        },
        {
          id: 6,
          name: 'Utility',
          url: '#',
          image: require('@/assets/images/utility-market.jpg'),
        },
      ],
    };
  },
};
</script>

<style lang="scss">
@import '@/styles/_variables.scss';

// Product Markets Styles
.product-markets {
  padding: 0px 0;
  margin: 0 0 20px;

  @media(max-width: $tablet) {
    display: none;
  }

  &__heading {
    letter-spacing: 0.05em;
    color: #000;
  }

  &__cards {
    display: flex;
  }

  .card {
    width: calc(100% / 6 + 20px);
    text-decoration: none;
    box-shadow: $shadow;
    background-color: #fff;
    margin: 0 10px;
    box-sizing: border-box;
    padding: 0;
    display: inline-block;
    transition: all 0.3s;
    cursor: pointer;

    &:hover {
      transform: scale(1.05);
    }
    
    &:first-child {
      margin-left: 0;
    }
    &:last-child {
      margin-right: 0;
    }

    &__image {
      background-color: #eee;
      padding-bottom: 70%;
      display: block;
      background-repeat: no-repeat;
      background-position: center;
      background-size: cover;
    }
    &__content {
      text-decoration: none;
      font-weight: 700;
      padding: 10px 10px;
      margin: 0;
      vertical-align: middle;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 30%;
      color: #000;
      p {
        display: block;
        margin: 0;
        font-weight: 700;
      }
    }
  }
}
</style>
