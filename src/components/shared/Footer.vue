<template>
  <footer id="footer" class="footer">
      <h3 class="footer__heading">Support Center</h3>
      <a class="footer__number" href="tel:800-257-5288">800-25-Platt</a>
      <a class="footer__number footer__number--full" href="tel:800-257-5288">800-257-5288</a>

      <p class="footer__info">
      4 a.m. - 12 a.m. (pst)<br>
      7 Days a week
      </p>
      

      <button v-on:click="triggerLiveChat" class="footer__live-help">
        <LiveHelpIcon/> 
        <span>Live Help</span>
      </button>

      <nav id="footer-navigation" class="footerNav">
          <ul class="footerNav__list">
              <li class="footerNav__item">
                  <a href="#" class="footerNav__link">Contact Us</a>
              </li>
              <li class="footerNav__item">
                  <a href="#" class="footerNav__link">What's New</a>
              </li>
              <li class="footerNav__item">
                  <a href="#" class="footerNav__link">FAQ's</a>
              </li>
          </ul>
      </nav>
  </footer>
</template>

<script>
import LiveHelpIcon from '../../assets/icons/ic_chat.svg';

export default {
  methods: {
    triggerLiveChat: () => {
      // eslint-disable-next-line
      alert('Live Chat would pop up here...');
    },
  },
  components: {
    LiveHelpIcon,
  },
};
</script>

<style lang="scss">
@import '@/styles/_variables.scss';

.footer {
    background-color: $dkGray;
    padding: 20px;
    color: #fff;

    &__live-help {
      border-radius: 30px;
      background-color: $ltGray;
      display: flex;
      justify-content: center;
      align-items: center;
      margin: 40px auto 70px;
      padding: 10px 50px;
      color: #000;
      border: 0;
      transition: all 0.3s;
      &:focus {
        outline: none;
      }

      svg {
        fill: #000;
        height: 30px;
        width: 30px;
        margin-right: 15px;
        transition: all 0.3s;
      }

      &:hover {
        background-color: $plattGreen;
        color: #fff;
        svg {
          fill: #fff;
        }
      }
    }

    &__number {
      font-weight: 700;
      text-decoration: none;
      display: block;
      font-size: 120%;

      &--full {
        font-size: 80%;
        font-weight: 400;
        margin: 0 0 20px;
      }
    }

    &__info {
      font-weight: 700;
    }

    .footerNav {
      box-sizing: border-box;
      padding: 0 20px;
      max-width: 100%;
      width: 560px;
      display: block;
      margin: 0 auto;

      &__list {
        display: flex;
        justify-content: space-between;
        align-items: center;
        list-style-type: none;
        margin: 0;
        padding: 0;
      }
      
      &__item {
        display: inline-block;
      }

      &__link {
        color: #fff;
        text-decoration: none;
        font-weight: 700;
        font-size: 120%;
        transition: all 0.3s;

        &:hover {
          opacity: 0.6;
        }
      }
    }
}

</style>
