<template>
  <p>
    {{ convertToDoller(amount) }}
  </p>
</template>

<script>
export default {
  props: ['amount'],
  data() {
    return {
      rate: 370
    };
  },
  methods: {
    convertToDoller(value) {
      return Number.parseFloat(value).toFixed(2);
    }
  }
};
</script>

<style></style>
