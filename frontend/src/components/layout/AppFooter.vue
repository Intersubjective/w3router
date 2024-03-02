<script setup>
import { store } from '@/store';
</script>

<template>
  <footer class="w3-footer">
    <nav>
      <router-link
        to="/"
        class="w3-footer__home-link"
      >
        W3 Router
      </router-link>
      <div class="w3-footer__central-navigation">
        <router-link
          to="/"
          class="w3-footer__link"
        >
          Network monitor
        </router-link>
        <router-link
          :to="{ name: 'home', hash: '#about', params: { blockchain: store.activeBlockchain } }"
          class="w3-footer__link"
        >
          About RPC
        </router-link>
        <router-link
          :to="{ name: 'home', hash: '#steps', params: { blockchain: store.activeBlockchain } }"
          class="w3-footer__link"
        >
          Set up Router
        </router-link>
        <router-link
          :to="{ name: 'home', hash: '#faq', params: { blockchain: store.activeBlockchain } }"
          class="w3-footer__link"
        >
          FAQ
        </router-link>
      </div>
      <a class="w3-footer__copyright">© 2024 W3 Router</a>
    </nav>
  </footer>
</template>

<style lang="scss">
@import "@/assets/colors.scss";
@import "@/assets/breakpoints.scss";

.w3-footer {
  padding-bottom: 1rem;
  padding-top: 1rem;
  background: $gray-50;

  .w3-footer__central-navigation {
    display: none;
  }

  .w3-footer__home-link {
    padding-left: 1rem;
    display: none;
  }

  .w3-footer__link {
    color: $color-text;
    font-weight: 600;
    font-size: 1rem;
    text-decoration: none;
  }

  .w3-footer__switch {
    display: none;
  }

  .w3-footer__copyright {
    color: $gray-500;
    font-size: 16px;
    font-weight: 400;
    line-height: 24px;
    display: flex;
    justify-content: center;
    padding-right: 1rem;
    cursor: default;
  }
}

@media (min-width: $breakpoint-desktop) {
  .w3-footer {
    padding-bottom: 2rem;
    padding-top: 2rem;

    nav {
      max-width: calc(1216px + 4rem);
      margin: 0 auto;
      padding: 0 1rem;
      display: flex;
      gap: 1.5rem;
      justify-content: space-between;
      align-items: center;
      align-content: center;
    }

    .w3-footer__central-navigation {
      display: flex;
      gap: 1.5rem;
      justify-content: center;
    }

    .w3-footer__home-link {
      display: initial;
      color: $color-text-heading;
      text-decoration: none;
      font-size: 1.25rem;
      line-height: 1.5rem;
      font-weight: 600;
      width: 15rem;
    }

    .w3-footer__switch {
      display: flex;
    }
  }
}
</style>
