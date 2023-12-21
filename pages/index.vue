<template>
  <main class="page">
    <div class="container">
      <h1 class="headline">
        <img src="~assets/images/salvem-escoles.svg" alt="Salvem Escoles" class="headline-title" />
        <span class="headline-warning">
          <img src="~assets/images/warning.png" alt="Alerta" />
          Centres educatius en perill
          <img src="~assets/images/warning.png" alt="Alerta" />
        </span>
      </h1>

      <section class="card rounded shadow intro">
        <h2 class="intro-title">El govern de Mazón (PP i VOX) ha anunciat retallades en el pressupost d’Educació</h2>

        <p class="intro-text">
          El govern del Botànic va deixar planificada la construcció i reforma de centres educatius fins al 2027. 
          Ara, PP i Vox volen desfer tot això amb unes retallades que posen en perill centenars de
          centres edicatius que ja contaven amb aquestes millores. Altres, directament, no es construiran.
        </p>

        <div class="facts">
          <article class="fact">
            <AnimatedNumber class="fact-number" :from="0" :to="341" />
            <span class="fact-text">Centres educatius en perill</span>
          </article>

          <article class="fact">
            <AnimatedNumber class="fact-number" :from="0" :to="174" />
            <span class="fact-text">Municipis afectats</span>
          </article>

          <article class="fact full">
            <AnimatedNumber class="fact-number" :from="0" :to="1400" append="M €" />
            <span class="fact-text">Adjudicats per a construcció i millores d'escoles que no s’executaran</span>
          </article>

          <article class="fact full">
            <AnimatedNumber class="fact-number" :from="0" :to="35000" />
            <span class="fact-text">Llocs de treball de la construcció afectats directament o indirectament.</span>
          </article>
        </div>
      </section>

      <section class="amiguitos">
        <p class="text">
          A més, han clavat un canvi de normativa que els permetrà no seguir criteris tècnics
          per a decidir quins centres necessiten més rebre reformes o millores i poder
          fer-ho directament a dit. Així podran beneficiar als seus "amiguitos".
        </p>
      </section>

      <section class="centre-list">
        <h2 class="centre-list-title">Consulta si el teu centre<br>està en perill</h2>

        <Centres />
      </section>

      <section class="longass-list">
        <p class="text">
          Una llista tan llarga que ocupava <span class="meters">&lt;- 8m -&gt;</span> quan la vam traure
          a les Corts. I quasi tan gran com la cara de vergonya de Mazón i el Conseller d'Educació.
        </p>

        <iframe width="560" height="315" src="https://www.youtube.com/embed/_lrKUOjpQKA?si=2mvvrI3sLjd1PVJW" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>
      </section>
    </div>
  </main>
</template>

<style lang="scss">
.page {
  position: relative;
  margin-top: 15rem;
  z-index: 1;
}

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

.text {
  font-size: var(--text-xl);
}

.intro {
  margin: 6rem auto;
  font-size: var(--text-md);

  &-title {
    font-size: var(--text-2xl);
    letter-spacing: -.03em;
  }

  &-text {
    margin-top: 3rem;
  }
}

.facts {
  display: grid;
  grid-template-columns: 1fr 1fr;
  margin: calc(var(--card-padding) * -1);
  margin-top: var(--card-padding);
}

.fact {
  padding: var(--card-padding);
  border-top: 1px var(--gray-300) solid;

  &-number {
    display: block;
    font-weight: bold;
    font-size: var(--text-3xl);
    font-weight: 900;
    letter-spacing: -.03em;
    line-height: 1.1;
  }

  &-text {
    display: block;
    line-height: 1.25;
  }

  &.full {
    grid-column: span 2;
  }
}

.amiguitos {
  max-width: var(--max-width);
  margin: 0 auto;
}

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

.centre-list {
  max-width: var(--max-width);
  margin: 6rem auto;

  &-title {
    font-size: var(--text-2xl);
    margin-bottom: 2rem;
  }
}
</style>