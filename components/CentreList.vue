<template>
  <section class="centre-list">
    <h2 class="centre-list-title">
      {{ $t('centres.title') }}
    </h2>

    <Centres />
  </section>
</template>

<style lang="scss" scoped>
.centre-list {
  max-width: var(--max-width);
  margin: 6rem auto;

  &-title {
    font-size: var(--text-2xl);
    margin-bottom: 2rem;
    max-width: 500px;
    text-wrap: balance;
  }
}
</style>