<template>
  <main>
    <nav-bar current-page="Posts" />
    <posts-feed />
  <back-to-top-button />
    <footer-bar current-page="Posts" />
  </main>
</template>

<script>
import NavBar from '@/components/NavBar.vue';
import postsFeed from '@/components/PostsFeed.vue';
import FooterBar from '@/components/FooterBar.vue';
import BackToTopButton from '@/components/BackToTopButton.vue';

export default {
  name: 'posts',
  components: {
    NavBar,
    postsFeed,
    BackToTopButton,
    FooterBar
  },
};
</script>
