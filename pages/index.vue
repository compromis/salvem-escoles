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
  margin-top: 15rem;
  z-index: 1;
}

.text {
  font-size: var(--text-xl);
}
</style>