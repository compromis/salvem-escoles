<script setup>
import Centres from '~/data/centres.js'
</script>

<template>
  <div class="card shadow rounded">
    <table>
      <tr v-for="centre in Centres" :key="centre.Centre">
        <td>{{ centre.Municipality }}</td>
        <td>{{ centre.Centre }}</td>
      </tr>
    </table>
  </div>
</template>