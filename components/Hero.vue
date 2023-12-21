<template>
  <h1 class="headline">
    <img src="~assets/images/salvem-escoles.svg" :alt="$t('header.title')" class="headline-title" />
    <span class="headline-warning">
      <img src="~assets/images/warning.png" alt="Alerta" />
      {{ $t('header.warning') }}
      <img src="~assets/images/warning.png" alt="Alerta" />
    </span>
  </h1>
</template>

<style lang="scss" scoped>
.headline {
  text-align: center;

  &-title {
    width: 100%;
    max-width: var(--max-width);
  }

  &-warning {
    display: flex;
    background: var(--blue);
    align-items: center;
    gap: 1rem;
    padding: 1rem 2rem;
    border-radius: 20rem;
    width: fit-content;
    margin: 4rem auto;
    text-wrap: balance;
    font-size: var(--text-xl);
    letter-spacing: -.03em;

    img {
      height: 1em;
    }
  }
}
</style>