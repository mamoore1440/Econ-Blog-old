<template>
  <main>
    <nav-bar current-page="Current Events" />
    <current-events-feed />
  <back-to-top-button />
    <footer-bar current-page="Current Events" />
  </main>
</template>

<script>
import NavBar from '@/components/NavBar.vue';
import CurrentEventsFeed from '@/components/CurrentEventsFeed.vue';
import FooterBar from '@/components/FooterBar.vue';
import BackToTopButton from '@/components/BackToTopButton.vue';

export default {
  name: 'current-events',
  components: {
    NavBar,
    CurrentEventsFeed,
    BackToTopButton,
    FooterBar
  },
};
</script>
