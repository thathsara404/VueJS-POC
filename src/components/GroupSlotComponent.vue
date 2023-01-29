<template>
  <div class="col-md-12">
    <!-- ACCESS GROUP SLOT COMPONENT -->
    <h1><slot name="header" class="header"></slot></h1>
    <p><slot class="default">Body</slot></p>
    <h1><slot name="footer" class="footer"></slot></h1>
  </div>
</template>

<script>
export default {
  name: 'GroupSlotComponent',
  props: [],
  components: {},
  data() {
    return {
    };
  },
  methods: {
  }
};
</script>

<style>
  .header {
    color: aqua;
  }
  .footer {
    color: blueviolet;
  }
</style>
