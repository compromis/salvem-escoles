<script setup>
import Centres from '~/data/centres.js'

const filter = ref('')
const filteredCentres = computed(() => {
 return Centres.filter((centre) => {
  const normalizedFilter = filter.value.normalize("NFD").replace(/[\u0300-\u036f]/g, "").toUpperCase()
  const normalizedMunicipality = centre.Municipality.normalize("NFD").replace(/[\u0300-\u036f]/g, "").toUpperCase()
  const normalizedName = centre.Name.normalize("NFD").replace(/[\u0300-\u036f]/g, "").toUpperCase()
  return normalizedName.includes(normalizedFilter) || normalizedMunicipality.includes(normalizedFilter)
 })
})
</script>

<template>
  <div class="centres card shadow rounded">
    <form class="centres-filter">
      <input
        type="search"
        v-model="filter"
        placeholder="Troba el teu centre...">
        <SearchIcon class="centres-icon" />
    </form>
    <table class="centres-table table">
      <colgroup>
        <col width="35%">
        <col width="75%">
      </colgroup>
      <thead>
        <tr>
          <th>Municipi</th>
          <th>Centre</th>
        </tr>
      </thead>
      <tbody v-if="filteredCentres.length">
        <tr v-for="centre in filteredCentres" :key="centre.Centre">
          <td>{{ centre.Municipality }}</td>
          <td>{{ centre.Name }}</td>
        </tr>
      </tbody>
      <tbody v-else>
        <tr>
          <td colspan="2" class="no-results">
            De moment tens sort...
          </td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<style lang="scss">
.centres {
  padding: 0;
  overflow: clip;

  &-table {
    td, th {
      padding: .75rem 1.25rem;
    }

    .no-results {
      text-align: center;
      color: var(--gray-600);
      font-size: 2rem;
      padding: 3rem 0;
    }
  }

  &-filter {
    position: relative;
    border-bottom: 1px solid var(--gray-300);

    input {
      display: block;
      appearance: none;
      padding: 1.25rem;
      padding-left: 3.25rem;
      width: 100%;
      border: 0;
      font-size: 1.75rem;
      color: var(--gray-900);

      &::placeholder {
        color: var(--gray-600);
      }

      &:focus {
        background: var(--gray-50);
        outline: 0;
      }
    }

    .centres-icon {
      position: absolute;
      top: 50%;
      left: 1.25rem;
      transform: translate(0, -50%);
      pointer-events: none;
      height: 1.25rem;
      width: 1.25rem;
      color: var(--gray-600);
    }

    &:has(input:not(:placeholder-shown)) {
      .centres-icon {
        color: var(--gray-900);
      }
    }
  }
}
</style>