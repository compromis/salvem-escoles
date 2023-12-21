<template>
  <main>
    <img src="~assets/images/wrecking-ball.svg" alt="Una grua derriba el titol de Salvem Escoles" class="wrecking-ball" />
    <img src="~assets/images/crane.svg" alt="Grua" class="crane" />
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
          Unes retallades que afectaran principalment al manteniment i construcció de centres educatius.
        </p>

        <div class="facts">
          <article class="fact">
            <AnimatedNumber class="fact-number" :from="0" :to="341" />
            <span class="fact-text">centres educatius en perill</span>
          </article>

          <article class="fact">
            <AnimatedNumber class="fact-number" :from="0" :to="174" />
            <span class="fact-text">municipis afectats</span>
          </article>

          <article class="fact full">
            <AnimatedNumber class="fact-number" :from="0" :to="1400" append="M €" />
            <span class="fact-text">adjudicats i que no s’executaran</span>
          </article>

          <article class="fact full">
            <AnimatedNumber class="fact-number" :from="0" :to="35000" />
            <span class="fact-text">llocs de treball de la construcció afectats directament o indirectament.</span>
          </article>
        </div>
      </section>

      <section class="centre-list">
        <h2 class="centre-list-title">Consulta si el teu centre<br>està en perill</h2>

        <Centres />
      </section>
    </div>
  </main>
</template>

<style lang="scss">
main {
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
    font-size: 2rem;
    letter-spacing: -.03em;

    img {
      height: 1em;
    }
  }
}

.intro {
  margin: 6rem auto;
  font-size: 1.5rem;

  &-title {
    font-size: 3rem;
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
    font-size: 4rem;
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

.centre-list {
  max-width: var(--max-width);
  margin: 6rem auto;

  &-title {
    font-size: 3rem;
    margin-bottom: 2rem;
  }
}

.wrecking-ball {
  position: fixed;
  top: 5rem;
  left: 0;
  width: 25vw;
  z-index: 0;
}

.crane {
  position: fixed;
  right: 0;
  bottom: 0;
  width: 25vw;
  z-index: 0;
}
</style>