<script setup>
import IconGlobe from '@/assets/icons/contacts/icon-globe.svg';
import IconMail from '@/assets/icons/contacts/icon-mail.svg';
import IconTwitter from '@/assets/icons/contacts/icon-twitter.svg';

import IconMetamask from '@/assets/icons/wallets/icon-metamask.svg';
import IconRainbow from '@/assets/icons/wallets/icon-rainbow-2.svg?skipsvgo';
import IconPhantom from '@/assets/icons/wallets/icon-phantom.svg';
import IconCoinbase from '@/assets/icons/wallets/icon-coinbase.svg?skipsvgo';
import IconTrustWallet from '@/assets/icons/wallets/icon-trust.svg?skipsvgo';
import IconSafe from '@/assets/icons/wallets/icon-safe.svg';
import AppHeadingText from '@/components/shared/AppHeadingText.vue';

const SOCIALS = [
  {
    icon: IconGlobe,
    title: 'w3router',
    link: '',
  },
  {
    icon: IconMail,
    title: 'vadim@intersubjective.space',
    link: 'mailto:vadim@intersubjective.space',
  },
  {
    icon: IconTwitter,
    title: '@',
    link: 'https://twitter.com/',
  },
]

const WALLETS = [
  {
    icon: IconMetamask,
    title: 'Metamask',
    link: 'https://support.metamask.io/hc/en-us/articles/360043227612-How-to-add-a-custom-network-RPC',
  },
  // {
  //   icon: IconRainbow,
  //   title: 'Rainbow',
  //   link: 'https://rainbow.me/',
  // },
  // {
  //   icon: IconPhantom,
  //   title: 'Phantom Wallet',
  //   link: 'https://phantom.app/',
  // },
  {
    icon: IconCoinbase,
    title: 'Coinbase Wallet',
    link: 'https://www.coinbase.com/learn/wallet/How-to-add-custom-networks-Coinbase-Wallet',
  },
  {
    icon: IconTrustWallet,
    title: 'Trust Wallet',
    link: 'https://community.trustwallet.com/t/how-to-add-a-custom-network-on-the-trust-wallet-mobile-app/626781 ',
  },
  // {
  //   icon: IconSafe,
  //   title: 'Safe',
  //   link: 'https://safe.gnosis.io/',
  // },
]


</script>

<template>
  <section id="steps" class="home-content-steps">
    <AppHeadingText>Experience Unparalleled Trust</AppHeadingText>
    <div class="home-content-steps__wrapper">
      <div>
        <h2 class="home-content-steps__step-header">Step 1: Contact Us</h2>
        <p>
          For now, to maintain the highest standards of service and security,
          we're rolling out our RPC access on an individual basis.
          Connect with us through your preferred platform below:
        </p>
        <ul>
          <li v-for="social in SOCIALS">
            <a :href="social.link" target="_blank" rel="noopener noreferrer">
              <component :is="social.icon" />
              <span> {{ social.title }}</span>
            </a>
          </li>
        </ul>
      </div>
      <div>
        <h2 class="home-content-steps__step-header">Step 2: Set up RPC</h2>
        <p>
          Setting up W3 Router RPC is straightforward.
          Simply follow the instructions specific to your wallet.
          For convenience, here are guides for popular Polygon wallets you might be using:
        </p>
        <ul>
          <li v-for="wallet in WALLETS">
            <a :href="wallet.link" target="_blank" rel="noopener noreferrer">
              <component :is="wallet.icon" />
              <span> {{wallet.title}} </span>
            </a>
          </li>
        </ul>
      </div>
    </div>
  </section>
</template>

<style lang="scss">
@import '@/assets/colors.scss';
@import '@/assets/breakpoints.scss';

.home-content-steps {
  padding: 1.5rem;
  border-radius: 0.75rem;
  background: $gray-50;
  margin: 3rem 0;

  .home-content-steps__heading-text {
    color: $primary-700;
    font-size: 1rem;
    font-style: normal;
    font-weight: 600;
    line-height: 1.5rem;
    padding-bottom: 0.75rem;
  }

  .home-content-steps__wrapper {
    display: flex;
    flex-direction: column;
    gap: 4rem;
    background: $gray-50;
  }

  .home-content-steps__step-header {
    padding-bottom: 1.25rem;
  }

  ul {
    display: flex;
    flex-flow: column wrap;
    gap: 0.75rem 2rem;
    padding: 2rem 0 0;
    align-content: flex-start;
  }

  li {
    list-style: none;
    max-width: 14rem;
  }

  a {
    color: $color-text;
    text-decoration: none;
    display: flex;
    align-items: flex-start;
    gap: 0.75rem;
  }
}

@media screen and (min-width: $breakpoint-tablet) {
  .home-content-steps {
    padding: 2rem;

    ul {
      max-height: calc(3 * (3rem));
    }
  }
}

@media screen and (min-width: $breakpoint-desktop) {
  .home-content-steps {
    padding: 4rem;
    margin: 3rem 0;

    .home-content-steps__wrapper {
      flex-direction: row;
    }
  }
}
</style>
