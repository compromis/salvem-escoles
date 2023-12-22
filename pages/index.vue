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