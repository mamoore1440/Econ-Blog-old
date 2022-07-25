<template>
  <main>
    <nav-bar current-page="Breakdowns" />
    <breakdowns-feed />
  <back-to-top-button />
    <footer-bar current-page="Breakdowns" />
  </main>
</template>

<script>
import NavBar from '@/components/NavBar.vue';
import BreakdownsFeed from '@/components/BreakdownsFeed.vue';
import FooterBar from '@/components/FooterBar.vue';
import BackToTopButton from '@/components/BackToTopButton.vue';

export default {
  name: 'breakdowns',
  components: {
    NavBar,
    BreakdownsFeed,
    BackToTopButton,
    FooterBar
  },
};
</script>
