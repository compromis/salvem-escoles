<template>
  <section class="longass-list">
    <p class="text">
      Una llista tan llarga que ocupava <span class="meters">&lt;- 8m -&gt;</span> quan la vam traure
      a les Corts i quasi tan gran com la cara de vergonya de Mazón i el Conseller d'Educació.
    </p>

    <iframe width="560" height="315" src="https://www.youtube.com/embed/hBo4Hpfon1Q" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>
  </section>
</template>

<style lang="scss" scoped>
.longass-list {
  iframe {
    aspect-ratio: 16 / 9;
    height: 100%;
    width: 100%;
    margin-top: 3rem;
    border-radius: 1rem;
  }

  .text {
    max-width: var(--max-width);
    margin: 0 auto;
  }
}

.meters {
  border: 2px var(--white) solid;
  padding: .25rem 1rem;
  border-radius: 10rem;
  margin: 0 1rem;
}
</style>