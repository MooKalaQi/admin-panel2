<template>
  <Header name="Exchange"></Header>

  <div class="container">
    <p class="fs-3">Here you can exchange your money to whatever you want.</p>
    <form>
      <label for="YourCurrency">Amount You want to exchange: </label>

      <div class="d-flex flex-row col-8">
        <input
          class="w-75"
          type="range"
          name="YourCurrency"
          v-model="exchangedBalance"
          :max="balance.balance"
          :min="0"
          @change="handleChange()"
        />
        <input class="w-25" type="number" v-model="exchangedBalance" />
      </div>
    </form>
    <div class="to_currency d-flex align-items-center fs-1" >
      To : 
        <div class="currencies w-50 d-flex flex-row justify-content-between">
        <select id="ExchangeTo">
          <option
            v-for="currency in currencies"
            :key="currency.indexOf"
            :value="currency"
            :v-model="currency"
          >{{ currency.toUpperCase() }}</option>
        </select>

      </div>
    </div>
  </div>
</template>
<script>
import Header from '../components/Header.vue';
import sourceData from '../data.json';
export default {
  data() {
    return {
      balance: sourceData.dashboard[0],
      currencies: sourceData.currencies,
      exchangedBalance: 0,
      isActive: false,
    };
  },
  components: {
    Header,
  },
  methods: {
    selectedCurrency(event) {
      console.log(event);
      this.isActive = !this.isActive;
    },
    handleChange(exchangedBalance) {
      console.log(exchangedBalance);
    },
  },
};
</script>
<style scoped>
.show {
  background-color: inherit;
}
.dropdown_item {
  text-decoration: none;
  color: #1f1f1f;
}
.currencies > button {
  width: 10rem;
  height: 5rem;
  border: none;
  background-color: #ff8400;
  font-weight: bold;
  border-radius: 5px;
}
select{
    width: 10rem;
    height: 5rem;
    font-size: 1.5rem;
    font-weight: bold;
}
option{
    font-size: 1.2rem;
}
input[type=range]{
    accent-color: #ff0000;
}
input[type=number]{
    text-align: center;
    font-size: 1.1rem;
}
</style>
