<template>
  <section class="quick-links">
      <a v-for="link in quickLinks" v-bind:key="link.name + link.id" :href="link.url" class="card">
        <div class="card__image" :style="{ 'background-image': `url(${link.image })` }"></div>
        <div class="card__content">
          <p>{{ link.name }}</p>
        </div>
      </a>
  </section>
</template>

<script>
export default {
  data: () => ({
    quickLinks: [
      {
        id: 1,
        name: 'Super Tool Day & Dynamic Data Day',
        url: '#',
        image: require('@/assets/images/super-tool-quick-link.jpg'),
      },
      {
        id: 2,
        name: 'Branch Locations',
        url: '#',
        image: require('@/assets/images/branch-locations-quick-link.jpg'),
      },
      {
        id: 3,
        name: 'Help Center',
        url: '#',
        image: require('@/assets/images/help-center-quick-link.jpg'),
      },
      {
        id: 4,
        name: 'Platt University',
        url: '#',
        image: require('@/assets/images/platt-university-quick-link.jpg'),
      },
    ],
  }),
};
</script>

<style lang="scss">
@import '@/styles/_variables.scss';

// Quick links Styling 
.quick-links {
  display: flex;
  flex-wrap: wrap;
  margin: 0 0 20px;

  .card {
    width: calc(100% / 4 - 30px);
    text-decoration: none;
    box-shadow: $shadow;
    background-color: #fff;
    margin: 0 20px;
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
      background-color: #fff;
      padding-bottom: 100%;
      display: block;
      background-repeat: no-repeat;
      background-position: center;
      background-size: contain;
      margin: 0 10px;
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
      height: 20%;
      color: #000;
      p {
        display: block;
        margin: 0;
        font-weight: 700;
      }
    }

    @media(max-width: $tablet) {
      width: calc(100% / 2 - 10px);
      margin: 0 10px 20px;

      &:first-child {
        margin-left: auto;
      }
      &:last-child {
        margin-right: auto;
      }
      &:nth-of-type(2n - 1) {
        margin-left: 0;
      }
      &:nth-of-type(2n) {
        margin-right: 0;
      }

      &__content {
        height: auto;
      }
    }
  }
}
</style>
