<template>
  <div class="menuTable">
    <div class="menuTable__title">
      <img height="92px" width="82px" src="./tittleImg.png">
      <span v-text="'КАТАЛОГ ПРОДУКЦИИ'"></span>
    </div>
    <div class="menuTable__items">
      <menu-cell
        v-for="cell in cells"
        :key="cell.name"
        :item="cell"
      />
    </div>
  </div>
</template>

<script>
  import MenuCell from "./MenuCell";
  export default {
    name: "MenuTable",
      components: {MenuCell},
      data: () => ({
        cells: [
            {
                name: 'ИМИТАЦИЯ БРУСА'
            },
            {
                name: 'ПОГОНАЖНЫЕ ИЗДЕЛИЯ'
            },
            {
                name: 'ЕВРОВАГОНКА'
            },
            {
                name: 'ВАГОНКА ШТИЛЬ'
            },
            {
                name: 'ДОСКА ПОЛА'
            },
            {
                name: 'БРУСОК'
            },
            {
                name: 'БЛОК ХАУС'
            },
            {
                name: 'ЭЛЕТЕМЕНТЫ ЛЕСТНИЦ'
            },
        ]
    })
  }
</script>

<style lang="sass">
  .menuTable
    display: flex
    flex-direction: column
    background-image: url(FON.jpg)
    -moz-background-size: 100% /* Firefox 3.6+ */
    -webkit-background-size: 100% /* Safari 3.1+ и Chrome 4.0+ */
    -o-background-size: 100% /* Opera 9.6+ */
    background-size: 100% /* Современные браузеры */
    justify-content: center
    align-content: center
    &__title
      display: flex
      padding: 15px
      margin-left: -62px
      display: flex
      justify-content: center
      align-items: center
      color: white
      font-family: "BicubikRegular"
      font-size: 72px
      text-shadow: #00ca00 0px 0px 4px, #006f3a 0px 0px 7px
      > span
        margin-left: 20px
        line-height: 1
        filter: drop-shadow(-1px 9px 2px black)
    &__items
      display: flex
      flex-wrap: wrap
      justify-content: center
      align-self: center
      padding-right: 5%
      padding-right: 5%

</style>
