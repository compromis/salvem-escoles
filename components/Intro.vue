<template>
  <section class="card rounded shadow intro">
    <h2 class="intro-title">
      {{ $t('intro.title') }}
    </h2>

    <p class="intro-text">
      {{ $t('intro.text') }}
    </p>

    <div class="facts">
      <article class="fact">
        <AnimatedNumber class="fact-number" :from="0" :to="341" :duration="1.25" />
        <span class="fact-text">{{ $t('facts.schools_in_danger') }}</span>
      </article>

      <article class="fact">
        <AnimatedNumber class="fact-number" :from="0" :to="178" :duration=".75" />
        <span class="fact-text">{{ $t('facts.affected_municipalities') }}</span>
      </article>

      <article class="fact">
        <AnimatedNumber class="fact-number" :from="0" :to="1400" :duration="2.75" append="M €" />
        <span class="fact-text">{{ $t('facts.alloted_budget') }}</span>
      </article>

      <article class="fact">
        <AnimatedNumber class="fact-number" :from="0" :to="35000" :duration="2" />
        <span class="fact-text">{{ $t('facts.jobs_in_danger') }}</span>
      </article>
    </div>
  </section>
</template>

<style lang="scss" scoped>
.intro {
  margin: calc(2rem + 5vh) auto;
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
}

@include media-breakpoint-down(md) {
  .fact {
    grid-column: span 2;
  }
}
</style>