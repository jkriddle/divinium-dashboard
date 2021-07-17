<template>
  <div>
    <h1>Loan Calculator</h1>

    <div class="form">
       <div class="form-group">
          <label for="collateral">Collateral</label>
          <div class="input-group mb-2">
            <div class="input-group-prepend">
              <div class="input-group-text">$</div>
            </div>
            <input v-model="collateral" type="number" class="form-control" placeholder="500,000">
          </div>
      </div>

       <div class="form-group">
          <label for="collateral">Borrowed</label>
           <div class="input-group mb-2">
            <div class="input-group-prepend">
              <div class="input-group-text">Ξ</div>
            </div>
            <input v-model="borrowed" type="number" class="form-control" placeholder="100">
          </div>
      </div>

       <div class="form-group">
          <label for="collateral">Liquidation Threshold</label>
          <div class="input-group mb-2">
            <div class="input-group-prepend">
              <div class="input-group-text">%</div>
            </div>
            <input v-model="threshold" type="number" class="form-control" placeholder="82.5">
          </div>
      </div>

       <div class="form-group">
          <label for="collateral">Current Price</label>
          <div class="input-group mb-2">
            <div class="input-group-prepend">
              <div class="input-group-text">$</div>
            </div>
            <input v-model="price" type="number" class="form-control" placeholder="1900">
          </div>
      </div>
    </div>

    <div class="form mt-5">
      <h3>Calculations</h3>

       <div class="form-group">
          <label for="collateral">Loan-to-Value (LTV)</label>
          <div class="input-group mb-2">
            <div class="input-group-prepend">
              <div class="input-group-text">%</div>
            </div>
            <input v-model="ltv" disabled class="form-control" />
          </div>
      </div>

       <div class="form-group">
          <label for="collateral">Liquidation Price</label>
          <div class="input-group mb-2">
            <div class="input-group-prepend">
              <div class="input-group-text">$</div>
            </div>
            <input v-model="liquidationPrice" disabled class="form-control" />
          </div>
      </div>
    </div>

  </div>
</template>

<script>

export default {
  name: 'HelloWorld',
  props: {
    initialCollateral: Number,
    initialBorrowed: Number,
    initialThreshold: Number,
    initialPrice: Number
  },
  data: function () {
    return {
      collateral: this.initialCollateral,
      borrowed: this.initialBorrowed,
      threshold: this.initialThreshold,
      price: this.initialPrice,
    }
  },
  computed: {
    liquidationPrice: function() {
      return (this.collateral * (this.threshold/100) / this.borrowed).toLocaleString();
    },
    ltv: function() {
      return ((this.borrowed * this.price) / this.collateral * 100).toLocaleString();
    }
  }
}
</script>

<style scoped>

</style>
