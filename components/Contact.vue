<template>
  <section class="contact">
    <div class="outline-card">
      <div class="header">
        <h2>Bústia de consultes</h2>
        <p class="text">
          Hem habilitat esta bústia per escoltar els teus problemes, els teus dubtes i les teues solicituts per fer-les arribar a les Corts Valencianes.
        </p>

        <img src="../assets/images/mailbox.png" alt="" class="mailbox" />
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

    .header {
      position: relative;
      padding: 1.5rem;
    }

    h2 {
      padding-bottom: 0;
      margin-bottom: .5rem;
      max-width: 80%;
    }

    .text {
      margin: 0;
      max-width: 80%;
      font-size: var(--text-lg);
      margin-bottom: 2rem;
    }

    .mailbox {
      position: absolute;
      bottom: 0;
      right: 0;
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
</style>