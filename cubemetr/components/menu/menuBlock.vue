<template>
 <div class="menuBlock c-flex-column c-flex-align-items-center">
  <navigation :category="category" @change="changeActive"/>
   <div class="c-flex-column c-flex-align-items-end">
     <h2 class="menuBlock-header">Строганные <span class="yellow-text">материалы</span></h2>
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

</style>
