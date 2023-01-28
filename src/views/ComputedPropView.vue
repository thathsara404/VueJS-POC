<template>
  <div class="row">
    <h3>Parent Component</h3>
    <p>{{ names }}</p>
    <name-filter-component :names="names" @add-name-event="addToNamesArray($event)"/>
  </div>
</template>

<script>

import NameFilterComponent from '@/components/NameFilterComponent.vue';

export default {
  name: 'ComputedPropView',
  prop: [],
  components: {
    NameFilterComponent
  },
  data() {
    return {
      names: ['Saman', 'Daham']
    };
  },
  methods: {
    addToNamesArray(name) {
      this.names.push(name);
    }
  }
};
</script>
