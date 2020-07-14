<template>
  <div>
    <div class="autocomplete">
      <input
        type="text"
        v-model="search"
        @input="onChange"
        class="input-text"
      />
      <ul class="autocomplete-results" v-show="isOpen">
        <li 
          class="autocomplete-result" 
          v-for="(result,i) in results"
          :key="i"
           @click="setResult(result)"
        >
          {{result}}
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data() {
    return {
      search: '',
      results: [],
      items: ["Attack on Titan", "One Punch Man", "One Piece"],
      isOpen: false,
    };
  },
  methods: {
    onChange() {
      this.isOpen = true;
      this.filterResults();
    },
    filterResults() {
      this.results = this.items.filter(item => item.toLowerCase().indexOf(this.search.toLowerCase()) > -1);
    },
    setResult(result) {
      this.search = result;
      this.isOpen = false;
    },
  },
  props: {
  }
}
</script>

<style scoped>
  .autocomplete {
    position: relative;
    width: 1420x;
  }

  .autocomplete-results {
    padding: 0;
    margin: 0;
    border: 1px solid #eeeeee;
    height: 120px;
    overflow: auto;
  }

  .autocomplete-result {
    list-style: none;
    text-align: left;
    padding: 4px 2px;
    cursor: pointer;
  }

  .input-text {
    width: 1420px;
  }

  .autocomplete-result:hover {
    background-color: #4AAE9B;
    color: white;
  }
</style>
