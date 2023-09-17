<template>
    <h1 :class="[darkmode ? 'darkmode':'']">Add Your New Card Information :</h1>
    <form @submit="onSubmit" :class="[darkmode ? 'darkmode':'']">
      <label for="Card-number">Card Number: </label>
      <input type="number" name="Card-number" v-model="cardNumber" />
  
      <label for="cvv2">CVV2: </label>
      <input type="number" name="cvv2" v-model="cvv2" />
  
      <label for="exp">Expiration Date: </label>
      <input type="number" form="exp" v-model="expDate" />
  
      <label for="balance">Card Balance: </label>
      <input type="number" name="balance" v-model="balance" />
  
      <div>
        <label>Saving</label>
        <input type="checkbox" name="saving" v-model="saving" />
      </div>
  
      <input type="submit" value="Submit" />
    </form>
  </template>
  
  <script>
  import sourceData from '../data.json'
  export default {
    name: 'AddCard',
    data() {
      return {
        darkmode : sourceData.darkMode,
        cardNumber: '',
        cvv2: '',
        expDate: '',
        balance: '',
        saving: false,
      };
    },
    methods: {
      onSubmit(e) {
        e.preventDefault();
  
        if (!this.cardNumber || !this.cvv2 || !this.expDate) {
          alert('Please fill out all froms');
        }
        const newCard = {
          cardNumber: this.cardNumber,
          cvv2: this.cvv2,
          expDate: this.expDate,
          balance: this.balance,
          saving: this.saving,
        };
        this.$emit('add-card', newCard);
        (this.cardNumber = ''),
          (this.cvv2 = ''),
          (this.expDate = ''),
          (this.balance = ''),
          (this.saving = false);
      },
    },
    emits:['add-card']
  };
  </script>
  <style>
  .darkmode , .darkmode > * {
    background-color: #1f1f1f;
    color: #e8e8e8;
  }
  .darkmode > input {
    background-color: #333333!important ;
  }
  form {
    display: flex;
    flex-direction: column;
    align-items: center;
    margin-bottom: 5rem;
  }
  label {
    margin-top: 2rem;
    font-size: 1.3rem;
  }
  input {
    width: 75%;
    border: none;
    background: rgb(255, 255, 255);
    box-shadow: 1px 1px 5px 0px rgba(0, 0, 0, 0.233);
    height: 3rem;
    border-radius: 5px;
  }
  input[type='submit'] {
    background: teal;
    width: 50%;
    margin: auto;
    margin-top: 5rem;
    color: white;
    font-size: 1.5rem;
  }
  </style>
  