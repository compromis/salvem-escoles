<template>
  <section class="longass-list">
    <p class="text">
      Una llista tan llarga que ocupava <a href="https://www.tiktok.com/@compromis_net/video/7307297637080763680" target="_blank" class="meters">&lt;- 8m -&gt;</a> quan la vam traure
      a les Corts.
    </p>

    <iframe width="560" height="315" src="https://www.youtube-nocookie.com/embed/KoB4IXQhhE8" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>
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
    font-size: var(--text-xl);
  }
}

.meters {
  border: 2px var(--white) solid;
  padding: .25rem 1rem;
  border-radius: 10rem;
  margin: 0 .2em;
  white-space: nowrap;
  color: var(--white);

  &:hover {
    background: var(--white);
    color: var(--primary);
    text-decoration: none;
  }
}
</style>