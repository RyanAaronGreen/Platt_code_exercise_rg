<template>
  <section class="member">
    <div class="grid-container">
      <a href="" class="grid-item deals"></a>
      <div class="grid-item become-a-member">
        <img class="bamc__image" :src="require('@/assets/platt-plus.png')" alt="Platt Plus">
        <div class="become-a-member-content">
          <h3 class="bamc__heading">Get Started Today 
            <div class="bamc__heading_accent"> Become a <a href="">Platt Plus</a> Member.</div>
          </h3>
          <a href="#" class="bamc__cta">Learn More</a>
        </div>
      </div>
      <div class="grid-item recent-viewed"> 
        <div class="recent-viewed__heading">
          <h3>Recently Viewed</h3>
          <a href="#">View All</a>
        </div>

        <ul class="recently-viewed-list">
          <li v-for="viewed in recentlyViewed" :key="viewed.id" class="recently-viewed-item">
            <a :href="viewed.url">
              <img :src="viewed.imageUrl" :alt="viewed.name">
            </a>
          </li>
        </ul>
      </div>
    </div>
  </section>
</template>

<script>
export default {

  data() {
    return {
      recentlyViewed: [
        {
          id: 1,
          name: 'Product Name One',
          url: '#',
          imageUrl: require('@/assets/recent/11.png'),
        },
        {
          id: 2,
          name: 'Product Name Two',
          url: '#',
          imageUrl: require('@/assets/recent/22.png'),
        },
        {
          id: 3,
          name: 'Product Name Three',
          url: '#',
          imageUrl: require('@/assets/recent/22.png'),
        },
      ],
    };
  },

};
</script>

<style lang="scss">
@import '@/styles/_variables.scss';

// Member Area 
.member {
  margin: 0 0 20px;

  @media ( min-width: $tablet ) {  
    margin: 0;
  }
  .grid-container {
    display: grid;
    grid-template-areas: "deals" "members" "recently-viewed";
    grid-auto-rows: 50px; 
    grid-gap: 20px;
    grid-template-rows: auto auto auto;

  }

  .grid-item.deals {grid-area: deals;}
  .grid-item.become-a-member {grid-area: members;}
  .grid-item.recent-viewed {grid-area: recently-viewed;}

  @media ( min-width: $tablet ) {  
    .grid-container  {
      grid-template-areas: "members members" "deals recently-viewed";
      grid-template-rows: auto auto 0px;
      grid-template-columns: 1fr 1fr;
    }
  }

  .grid-item {
    background-color: #fff;
    box-shadow: $shadow;
    padding: 20px;
    color: #000;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
  }

  .grid-item.deals {
    grid-column: 1 / 1;
    background-image: url('../../assets/deal.png');
    background-size: cover;
    background-position: center;
    padding-top: 40%;
  }


  // Become a Member Styling
  .grid-item.become-a-member {
    flex-direction: column;
    align-items: center;
    justify-content: center;
    padding: 50px 20px;
    .bamc {
      &__image {
        display: block;
        margin: 0 0 20px;
      }
      &__heading {
        font-size: 120%;
        margin: 0 0 30px;

        &_accent {
          font-size: 80%;
          a {
            color: $plattGreen;
            text-decoration: none;;
          }
        }
      }

      &__cta {
        text-decoration: none;
        padding: 10px 60px;
        background-color: $ltGray;
        text-align: center;
        border-radius: 30px;
        border: 1px solid $ltGray;
        transition: all 0.3s;
        font-size: 90%;

        &:active,
        &:focus,
        &:hover {
          color: #fff;
          background-color: $plattGreen;
        }
      }
    }

    @media (min-width: $tablet) {
      grid-column: 1 / span 2;
      flex-direction: row;
      align-items: center;
      justify-content: space-around;
    }
  }

  // Recently Views Styling 

  .grid-item.recent-viewed {

    .recent-viewed__heading {
      width: 100%;
      display: flex;
      justify-content: space-between;
      align-items: flex-start; 
      margin: 0 0 10px;
      h3 {
        padding: 0;
        margin: 0;
      }
      a {
        font-weight: 700;
        color: $plattGreen;
        text-decoration: none;
      }
    }
    
    .recently-viewed-list {
      list-style-type: none;
      margin: 0;
      padding: 0;
      display: flex;
      justify-content: space-between;
      align-items: center;
    }

    .recently-viewed-item {
      margin: 0 5px;
    }
  }

}
</style>
