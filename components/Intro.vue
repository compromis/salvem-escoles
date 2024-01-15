<template>
  <section class="intro" id="intro">
    <article class="card rounded shadow intro-card">
      <h2 class="intro-title">
        {{ $t('intro.title') }}
      </h2>

      <p class="intro-text">
        {{ $t('intro.text') }}
      </p>

      <div class="facts">
        <div class="fact">
          <AnimatedNumber class="fact-number" :from="0" :to="341" :duration="1.25" />
          <span class="fact-text">{{ $t('facts.schools_in_danger') }}</span>
        </div>

        <div class="fact">
          <AnimatedNumber class="fact-number" :from="0" :to="178" :duration=".75" />
          <span class="fact-text">{{ $t('facts.affected_municipalities') }}</span>
        </div>

        <div class="fact">
          <AnimatedNumber class="fact-number" :from="0" :to="1400" :duration="2.75" append="M €" />
          <span class="fact-text">{{ $t('facts.alloted_budget') }}</span>
        </div>

        <div class="fact">
          <AnimatedNumber class="fact-number" :from="0" :to="35000" :duration="2" />
          <span class="fact-text">{{ $t('facts.jobs_in_danger') }}</span>
        </div>
      </div>
    </article>
    <aside class="video shadow">
      <IntroVideo />
      <!--<iframe width="315" height="560" src="https://www.youtube-nocookie.com/embed/OcHpmhwu1GE" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>-->
    </aside>
  </section>
</template>

<style lang="scss" scoped>
.intro {
  margin: calc(2rem + 5vh) 0;
  display: flex;
  gap: 1rem;

  &-title {
    font-size: var(--text-2xl);
    letter-spacing: -.03em;
  }

  &-text {
    margin-top: 2rem;
  }
}

.video {
  width: 100%;
  background: var(--gray-900);
  overflow: hidden;
  border-radius: 1rem;
  position: relative;

  iframe {
    display: block;
    height: 100%;
    width: 100%;
    aspect-ratio: 9 / 16;
  }
}

.intro-card {
  max-width: unset;
  display: flex;
  flex-direction: column;
}

.facts {
  display: grid;
  grid-template-columns: 1fr 1fr;
  margin: calc(var(--card-padding) * -1);
  margin-top: auto;
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
}

@media (max-width: 1200px) {
  .intro {
    flex-direction: column;
  }
}

@include media-breakpoint-down(md) {
  .fact {
    grid-column: span 2;
  }
}
</style>