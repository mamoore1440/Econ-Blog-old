<template>
  <main>
    <nav-bar :current-page="currentPage" />
    <posts-feed :section="section" />
    <back-to-top-button />
    <footer-bar :current-page="currentPage" />
  </main>
</template>

<script>
import NavBar from '@/components/NavBar.vue';
import PostsFeed from '@/components/PostsFeed.vue';
import FooterBar from '@/components/FooterBar.vue';
import BackToTopButton from '@/components/BackToTopButton.vue';

export default {
  name: 'section',
  components: {
    NavBar,
    PostsFeed,
    BackToTopButton,
    FooterBar
  },
  async asyncData({ $content, params, error }) {
    const slug = params.pathMatch.toLowerCase();

    const content = await $content('sections')
      .fetch()
      .catch((err) => {
        error({
          statusCode: 500,
          message: 'Something went wrong',
          error: err,
        });
      });

      const section = content?.sections?.find((section) => section.slug === slug);

      if (!section) {
        return error({ statusCode: 404, message: 'This section could not be found' });
      }

    return {
      section
    };
  },
  head() {
    return {
      title: this.section?.title || process.env.NUXT_ENV_SITE_NAME || process.env.NUXT_ENV_FULL_NAME,
    };
  },
  computed: {
    currentPage() {
      // return this.section?.title === 'Portfolio' ? 'Portfolio' : 'Breakdowns';
      return this.section?.title;
    }
  }
};
</script>
