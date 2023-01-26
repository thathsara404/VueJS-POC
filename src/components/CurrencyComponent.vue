<template>
  <form>
    <div class="form-group">
      <label for="currencyInput">Enter Your Amount (LKR)
        <input class="form-control" type="number" v-model="amount" name="amount" id="currencyInput" />
      </label>
    </div>
    <div>
      <label for="currencyType">State
        <select v-model="currencyType" id="currencyType" class="form-control">
          <option disabled>Choose...</option>
          <option value="Dollar">Dollar ($)</option>
          <option value="Euro">Euro (€)</option>
        </select>
      </label>
    </div>
  </form>
  <h3>
    Final Amount: {{ convert() }}
  </h3>
</template>

<script>
export default {
  props: [],
  data() {
    return {
      rate: [
        { name: 'Dollar', value: 370 },
        { name: 'Euro', value: 380 }
      ],
      currencyType: 'Dollar',
      amount: 0
    };
  },
  methods: {
    convert() {
      const selectedRate = this.rate.find((ctype) => ctype.name === this.currencyType).value;
      return Number.parseFloat(this.amount * selectedRate).toFixed(2);
    }
  }
};
</script>

<style>

</style>
