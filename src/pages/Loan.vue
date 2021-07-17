<template>
  <main-layout>
    <LoanCalculator 
      initial-collateral="584287.15" 
      initial-borrowed="185.003" 
      initial-threshold="82.5"
      initial-price="1903" />
  </main-layout>
</template>

<script>
import MainLayout from '../layouts/Main.vue'
import LoanCalculator from '../components/LoanCalculator'

export default {
  components: {
    MainLayout,
    LoanCalculator
  }
}
</script>