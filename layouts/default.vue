<script setup>
import BNav from '@compromis/blobby/components/nav/BNav.vue'
import BNavItem from '@compromis/blobby/components/nav/BNavItem.vue'
import BFooter from '@compromis/blobby/components/footer/BFooter.vue'
</script>

<template>
  <div>
    <BNav>
      <BNavItem href="#intro">
        Presentació
      </BNavItem>
      <BNavItem href="#centres">
        Centres en perill
      </BNavItem>
      <BNavItem href="#bustia">
        Bústia
      </BNavItem>

      <template #basic-nav>
        <BNavItem v-if="$route.path === '/cas'" href="/">
          <span class="d-none d-md-inline">Valencià</span>
          <span class="d-md-none">VAL</span>
        </BNavItem>
        <BNavItem v-else href="/cas">
          <span class="d-none d-md-inline">Castellano</span>
          <span class="d-md-none">CAS</span>
        </BNavItem>
      </template>
      <template #logo-append>{{ $t('header.title') }}</template>
    </BNav>

    <img src="~assets/images/wrecking-ball.svg" alt="Una grua derriba el titol de Salvem Escoles" class="wrecking-ball" />
    <img src="~assets/images/crane.svg" alt="Grua" class="crane" />

    <slot />
    <div class="container footer">
      <BFooter variant="dark" />
    </div>
  </div>
</template>

<style lang="scss">
.nav-logo-append {
  margin-left: 1rem;
}

.nav-padding {
  display: none;
}

.footer {
  color: var(--white);
  padding: 1rem;
}

.wrecking-ball {
  position: fixed;
  top: 5rem;
  left: 0;
  width: calc(100px + 20vw);
  z-index: 0;
}

.crane {
  position: fixed;
  right: 0;
  bottom: 0;
  width: calc(100px + 20vw);
  z-index: 0;
}

@include media-breakpoint-down(md) {
  .wrecking-ball {
    width: 55vw;
    top: 4rem;
  }

  .crane {
    width: 65vw;
    bottom: -1rem;
  }
}
</style>