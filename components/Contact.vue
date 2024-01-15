<template>
  <section class="contact" id="bustia">
    <div class="outline-card">
      <div class="header">
        <div class="header-content">
          <h2>{{ $t('contact.title') }}</h2>
          <p class="text">
            {{ $t('contact.text') }}
          </p>
        </div>
        <div class="header-image ms-auto">
          <img src="../assets/images/mailbox.png" alt="" class="mailbox" />
        </div>
      </div>
      <a href="mailto:salvemescoles@compromis.net" class="email">
        <span>-&gt;</span> salvemescoles@compromis.net
      </a>
    </div>
  </section>
</template>

<style lang="scss" scoped>
.contact {
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

    .mailbox {
      width: 10.5rem;
    }

    .email {
      display: flex;
      border-top: 2px var(--white) solid;
      color: var(--white);
      padding: 1.5rem;
      font-size: var(--text-lg);
      transition: .25s ease;
      align-items: center;
      border-radius: 0 0 .85rem .85rem;

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
}

@include media-breakpoint-down(md) {
  .contact {
    .header {
      flex-direction: column;

      &-image {
        margin-top: -3rem;
      }
    }
  }
}
</style>