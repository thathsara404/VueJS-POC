<template>
  <section class="name_filter_component">
    <h3>Child Component</h3>
    <div class="col-md-12">
      <section class="add_name">
        <div class="newName-group">
          <label for="addName">Enter New Name (Case Sensitive)
            <input class="form-control" type="text" v-model="newName" name="newName" id="newName" />
          </label>
        </div>
        <!-- Declare the addName EVENT -->
        <button class="btn btn-success"
         @click="$emit('addNameEvent', newName)">Add {{ newName }} To Parent Names Array</button>
      </section>
    </div>
    <div class="col-md-12">
      <section class="filter_name">
        <div class="form-group">
          <label for="searchName">Enter Your Name (Case Sensitive)
            <input class="form-control" type="text" v-model="searchName" name="searchName" id="searchName" />
          </label>
        </div>
        <ul>
          <li v-for="(item, index) in filteredNames" :key="index">{{ item }}</li>
        </ul>
        <button @click="searchTerm = searchName" class="btn btn-warning">Search</button>
      </section>
    </div>
  </section>
</template>

<script>
export default {
  name: 'NameFilterComponent',
  props: ['names'], // get the names array to sort
  data() {
    return {
      searchName: '', // input search name
      newName: '',
      searchTerm: ''
    };
  },
  computed: {
    filteredNames: {
      get() {
        console.log('Computed search (cache enabled version) functioning');
        // return filtered names in the names prop
        return this.names.filter((name) => name === this.searchTerm);
      },
      set() {
        // no need to set the prop for the moment
      }
    }
  }
};
</script>

<style lang="scss">

  $border: 1px solid black;
  $padding: 5px 10px;

  .name_filter_component {
    border: $border;
    padding: $padding;

    .add_name, .filter_name {
      padding: $padding;
    }
  }

</style>
