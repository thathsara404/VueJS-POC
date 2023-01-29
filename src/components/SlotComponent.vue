<template>
  <section class="slot_component">
    <h3>Child Component</h3>
    <div class="col-md-12">
      <!-- PASS SLOT DATA TO THE PARENT -->
      <h3>
        <slot v-bind:myNameSlot="name"></slot>
        <slot v-bind:myAddressSlot="address"></slot>
      </h3>
      <div class="form-group">
        <label for="nameText">Enter Your Name
          <input class="form-control" type="text" v-model="name" name="nameText" id="nameText" />
        </label>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'SlotComponent',
  props: [],
  components: {},
  data() {
    return {
      name: 'Thathsara',
      address: 'Galle'
    };
  },
  methods: {

  }
};
</script>

<style lang="scss">
  $border: 1px solid black;
  $padding: 10px 5px;

  .slot_component {
    border: $border;
    padding: $padding;
  }
</style>
