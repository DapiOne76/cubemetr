<template>
 <div class="navigation c-flex-justify-content-center c-flex-wrap">
   <div
     v-for="button in buttons"
     :key="button"
     :class="`navigation-button ${button === category ? 'active' : ''}`"
     @click="click(button)"
   >
    <span v-text="button"/>
   </div>
 </div>
</template>

<script>
  export default {
    name: "navigation",
    props: {
      category: String
    },
    data: () => ({
      buttons: [
        'ВСЕ',
        'СТРОГАННЫЕ МАТЕРИАЛЫ',
        'ПОГОНАЖ',
        'ЭЛЕМЕНТЫ ЛЕСТНИЦ',
        'МЕБЕЛЬНЫЙ ЩИТ'
      ]
    }),
    methods: {
      click(key) {
        this.$emit('change', key);
      }
    }
  }
</script>

<style lang="less">
  @import "../../pages/consts";
.navigation {
  width: 50%;
  &-button {
    -webkit-transition: background-color .2s,color .2s;
    transition: background-color .2s,color .2s;
    padding: 13px 20px 11px;
    font-size: 12px;
    background-color: hsla(0,0%,96.1%,.85);
    margin: 5px;
    cursor: pointer;
    border-radius: 5px;
    &.active,
    &:hover {
      background-color: @color-yellow;
    }
    &:hover {
      color: white;
    }
  }
}
  @media only screen and (max-width: 875px)  {
    .navigation{
      width: 250px;
    }
  }
</style>
