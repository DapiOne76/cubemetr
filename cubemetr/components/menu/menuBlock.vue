<template>
 <div class="menuBlock c-flex-column c-flex-align-items-center">
  <tovars :search="''" :category="category"/>
 </div>
</template>

<script>
  import Navigation from "./navigation";
  import Search from "./search";
  import Tovars from "./tovars";
  export default {
    name: "menuBlock",
    components: {Tovars, Search, Navigation},
    data: () => ({
      search: '',
      category: 'ВСЕ'
    }),
    methods: {
      changeActive(value) {
        this.category = value;
      },
      changeSearch(value) {
        this.search = value;
      }
    }
  }
</script>

<style lang="less">
  .menuBlock {
    margin-top: 50px;
    &-header {
      font-size: 56px;
      color: #01477f;
      margin-bottom: 20px;
    }
  }
  @media only screen and (max-width: 875px) {
    .menuBlock {
      &-header {
        font-size: 40px;
      }
    }
  }
</style>
