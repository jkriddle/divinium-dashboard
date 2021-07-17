<template>
  <ul>
    <li><v-link href="/">Home</v-link></li>
    <li><v-link href="/loan">Loan</v-link></li>
  </ul>

  <slot></slot>
</template>

<script>
import VLink from '../components/VLink.vue'

export default {
  components: {
    VLink
  }
}
</script>