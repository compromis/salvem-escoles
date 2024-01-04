<script setup>
const { t } = useI18n()

useSeoMeta({
  title: t('seo.title'),
  ogTitle: t('seo.title'),
  description: t('seo.description'),
  ogDescription: t('seo.description'),
  ogImage: 'https://salvemescoles.compromis.net/images/ogimage.png',
  twitterCard: 'summary_large_image',
})
</script>

<template>
  <main class="page">
    <div class="container">
      <Hero />
      <Intro />
      <CentreList />
      <LongassList />
    </div>
  </main>
</template>

<style lang="scss">
.page {
  position: relative;
  margin-top: calc(5rem + 10vh);
  z-index: 1;
}

.text {
  font-size: var(--text-xl);
}
</style>