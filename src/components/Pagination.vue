<template>
    <div class="pagination">
      <button
        v-if="showPrevious"
        class="item prev"
        @click="changePage(current - 1)"
      >
        &laquo;
      </button>
      <button
        v-for="(page, index) in pages"
        :key="page"
        class="item"
        :class="{ current: page === current }"
        @click="changePage(index)"
      >
        {{ page }}
      </button>
      <button v-if="showNext" class="item next" @click="changePage(current + 1)">
        &raquo;
      </button>
    </div>
  </template>
  
  <script>
  export default {
    name: 'Pagination',
    props: {
      offset: {
        type: [String, Number],
        default: 0,
      },
      total: {
        type: [String, Number],
        required: true,
      },
      limit: {
        type: [String, Number],
        default: 6,
      },
    },
    computed: {
      showPrevious() {
        return this.current > 1;
      },
      showNext() {
        return this.total > this.limit * this.current;
      },
      current() {
        return this.offset ? this.offset + 1 : 1;
      },
      pages() {
        const qty = Math.ceil(108 / 6);
        if (qty <= 1) return [1];
        return Array.from(Array(qty).keys(), (i) => i + 1);
      },
    },
    methods: {
      changePage(offset) {
        this.$emit('change-page', offset);
      },
    },
  };
  </script>

<style>

  .pagination {
    display: flex;
    align-items: center;
    justify-content: center;
    padding: 5em;
  }

  button{
    background-color: #FAFAFA;
    border-width: thin;
    border-color: #707070;
    width: 40px;
    height: 40px;
    font-family: 'Montserrat';
    font-weight: 600;
    font-size: 16px;
    cursor: pointer;
    color: #545454;
  }

  button:hover {
    background-color: #D2202C;
    color: #FFFFFF;
  
  }

</style>