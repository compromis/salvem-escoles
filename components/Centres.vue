<script setup>
import Centres from '~/data/centres.js'

const expanded = ref(false)
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
  <div
    id="centres"
    :class="['centres', 'card', 'shadow', 'rounded', { expanded: expanded || filter }]"
    @click="expanded = true">
    <form class="centres-filter">
      <input
        type="search"
        v-model="filter"
        :placeholder="$t('centres.filter')">
        <SearchIcon class="centres-icon" />
    </form>
    <table class="centres-table table">
      <colgroup>
        <col width="35%">
        <col width="75%">
      </colgroup>
      <thead>
        <tr>
          <th>{{ $t('centres.municipality') }}</th>
          <th>{{ $t('centres.name') }}</th>
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
            {{ $t('centres.no_results') }}
          </td>
        </tr>
      </tbody>
    </table>
  </div>
  <button @click="expanded = true" v-if="!expanded" class="expand">
    ↓ <span>Mostra tot el llistat</span> ↓
  </button>
</template>

<style lang="scss" scoped>
.centres {
  padding: 0;
  overflow: clip;
  max-height: 600px;
  transition: max-height 1s ease;

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

  &.expanded {
    max-height: 20000px;
  }
}

.expand {
  appearance: none;
  background-color: transparent;
  border: 0;
  color: var(--white);
  font-size: var(--text-lg);
  display: block;
  text-align: center;
  padding: 1rem;
  width: 100%;

  &:hover,
  &:focus {
    span {
      text-decoration: underline;
    }
  }
}
</style>