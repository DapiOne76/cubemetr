<template>
 <div class="menuBlock c-flex-column c-flex-align-items-center">
  <navigation :category="category" @change="changeActive"/>
   <div class="c-flex c-flex-justify-content-center">
     <search @change="changeSearch"/>
   </div>
  <tovars :search="search" :category="category"/>
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
      .targetBlock {
        &-img {
          max-height: 199px;
          max-width: 284px;
        }
      }
      &-header {
        font-size: 40px;
      }
    }
  }
</style>
