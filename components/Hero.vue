<template>
  <h1 class="headline">
    <img src="~assets/images/salvem-escoles.svg" :alt="$t('header.title')" class="headline-title" />
    <span class="headline-warning">
      <img src="~assets/images/warning.png" alt="Alerta" />
      {{ $t('header.warning') }}
      <img src="~assets/images/warning.png" alt="Alerta" />
    </span>
  </h1>
  <div class="cta">
    <a href="#centres">
      ↓ <span>{{ $t('header.cta') }}</span> ↓
    </a>
  </div>
</template>

<style lang="scss" scoped>
.headline {
  text-align: center;

  &-title {
    height: calc(15rem + 15vh);
  }

  &-warning {
    display: flex;
    background: var(--blue);
    align-items: center;
    gap: 1rem;
    padding: 1rem 2rem;
    border-radius: 20rem;
    width: fit-content;
    margin: 4rem auto 2rem;
    text-wrap: balance;
    font-size: var(--text-xl);
    letter-spacing: -.03em;

    img {
      height: 1em;
    }
  }
}

.cta {
  text-align: center;
  font-size: var(--text-lg);

  a {
    color: var(--white);

    &:hover {
      text-decoration: none;

      span {
        text-decoration: underline;
      }
    }
  }
}
</style>