<template>
  <section class="share">
    <div class="outline-card">
      <div class="header">
        <div class="header-content">
          <h2>{{ $t('share.title') }}</h2>
          <p class="text">
            {{ $t('share.text') }}
          </p>
        </div>
        <div class="header-image ms-auto">
          <img src="../assets/images/phone.png" alt="" class="phone" />
        </div>
      </div>
      <div class="share-links">
        <a href="whatsapp://send?text=https://salvemescoles.compromis.net" class="link whatsapp">
          <span>-&gt;</span> WhatsApp
        </a>
        <a href="https://t.me/share/url?url=https://salvemescoles.compromis.net&text=" class="link telegram">
          <span>-&gt;</span> Telegram
        </a>
        <a href="https://www.facebook.com/sharer/sharer.php?u=https://salvemescoles.compromis.net" class="link facebook">
          <span>-&gt;</span> Facebook
        </a>
        <a href="https://twitter.com/intent/tweet/?text=&url=https://salvemescoles.compromis.net&hashtags=SalvemEscoles" class="link twitter">
          <span>-&gt;</span> X / Twitter
        </a>
      </div>
    </div>
  </section>
</template>

<style lang="scss" scoped>
.share {
  margin: 6rem 0;

  .outline-card {
    max-width: var(--max-width);
    border: 2px var(--white) solid;
    border-radius: 1rem;
    margin: 0 auto;
    position: relative;
    background-color: rgba(#F16B14, .75);

    .header {
      position: relative;
      display: flex;
      gap: 1rem;

      &-content {
        padding: 1.5rem;
      }

      &-image {
        display: flex;
        align-items: end;
        transform: rotate(10deg) translate(1em, -1em);
      }
    }

    h2 {
      padding-bottom: 0;
      margin-bottom: .5rem;
    }

    .text {
      margin: 0;
      font-size: var(--text-lg);
    }

    .phone {
      width: 10.5rem;
    }

    .link {
      display: flex;
      border-top: 2px var(--white) solid;
      color: var(--white);
      padding: 1.5rem;
      font-size: var(--text-lg);
      transition: .25s ease;
      align-items: center;

      &:nth-child(odd) {
        border-right: 2px var(--white) solid;
      }

      &:hover {
        background: var(--white);
        color: var(--primary);
        text-decoration: none;

        span {
          width: 1.25em;
          transform: translateX(0);
        }
      }

      span {
        display: block;
        width: 0;
        overflow: hidden;
        transition: .5s ease;
        white-space: nowrap;
        transform: translateX(-100%);
      }
    }
  }

  &-links {
    display: grid;
    grid-template-columns: 1fr 1fr;

    .facebook {
      border-radius: 0 0 0 .85rem;
    }

    .twitter {
      border-radius: 0 0 .85rem 0;
    }
  }
}

@include media-breakpoint-down(md) {
  .share {
    .header {
      flex-direction: column;

      &-image {
        margin-top: -3rem;
      }
    }
  }
}
</style>