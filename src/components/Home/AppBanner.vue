<template>
  <section class="app-banner">
    <a href="#" class="card">
      <div class="card__image"></div>
      <div class="card__content">
        <p>Shop better, download the Platt app today!</p>
      </div>
    </a>
  </section>
</template>

<script>
export default {};
</script>

<style lang="scss">
@import '@/styles/_variables.scss';

.app-banner {
  .card {
    display: block;
    text-decoration: none;
    box-shadow: $shadow;
    background-color: #fff;

    &__image {
      background-color: #000;
      padding-bottom: 135px;
      display: block;
      background-image: url('../../assets/app-get-banner.png');
      background-repeat: no-repeat;
      background-position: center right;
      background-size: auto 100%;
    }
    &__content {
      text-decoration: none;
      font-weight: 700;
      padding: 5px 20px;
      color: #000;
    }
  }
}
</style>
