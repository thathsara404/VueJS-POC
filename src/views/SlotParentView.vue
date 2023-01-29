<template>
  <h3>Parent View</h3>
  <div class="row">
    <div class="col-md-12">
      <group-slot-component>
        <template #header>Header Text</template>
        <template #default></template>
        <template #footer>Footer Text</template>
      </group-slot-component>
    </div>
  </div>
  <div class="row">
    <div class="col-md-12">
      <label for="dataSelect">Select Data
        <select v-model="dataSelect" id="dataSelect" class="form-control">
          <option disabled>Choose...</option>
          <option value="name">Name</option>
          <option value="address">Address</option>
        </select>
      </label><br><br>
    </div>
  </div>
  <div class="row">
    <!-- ACCESS SLOT DATA OF A CHILD SLOT COMPONENT BASED ON THE PARENT REQUIREMENT-->
    <slot-component>
      <template v-slot="slotData">
        <div v-if="dataSelect === 'name'">
          {{ slotData.myNameSlot }}
        </div>
        <div v-else-if="dataSelect === 'address'">
          {{ slotData.myAddressSlot }}
        </div>
      </template>
    </slot-component>
  </div>
</template>

<script>
import SlotComponent from '@/components/SlotComponent.vue';
import GroupSlotComponent from '@/components/GroupSlotComponent.vue';

export default {
  name: 'CustomVModelView',
  props: [],
  components: { SlotComponent, GroupSlotComponent },
  data() {
    return {
      dataSelect: ''
    };
  },
  methods: {

  }

};
</script>

<style>

</style>
