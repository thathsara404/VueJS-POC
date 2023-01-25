<template>
  <div class="home">
    <div class="jumbotron">
      <h1 class="display-4">Simple Converter</h1>
      <p class="lead">This is a simple money converter app</p>
      <img :src="imgMoneySrc" :alt="imgMoneyAlt" />
      <hr class="my-4" />
      <h3>Points to remember</h3>
      <ul>
        <template v-for="(item, index) in importantPoints" :key="index">
          <li v-if="item.point !== 'Test'" :key="index">{{ item.point }} - {{ item.details }}</li>
        </template>
      </ul>
    </div>
    <currency-component amount="10" />
  </div>
</template>

<script>
// @ is an alias to /src
import CurrencyComponent from '@/components/CurrencyComponent.vue';
import imgMoney from '@/assets/imagemoney.png';

export default {
  name: 'HomeView',
  components: {
    CurrencyComponent
  },
  mounted() {
    setTimeout(() => {
      // Check, v-for support for array mutation. When mutation happen,
      // for loop will trigger automatically
      this.importantPoints[0].point = 'Authenticity';
    }, 5000);
  },
  data() {
    return {
      imgMoneySrc: imgMoney,
      imgMoneyAlt: 'This is a money image',
      importantPoints: [
        {
          point: 'Security',
          details: 'This is a secure app to conert your money.'
        },
        {
          point: 'Latest Rate',
          details: 'You will see the realtime rates here.'
        },
        {
          point: 'Test',
          details: 'This is for testing.'
        }
      ]
    };
  }
};
</script>
