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
        @clickOnCell="clickCell"
      />
    </div>
    <span class="menuTable--adwords" v-text="'Актуальные цены от 01.01.2020 года. Для строительных бригад, застройщиков и строительных компаний, предоставляется VIP скидка.'"></span>
  </div>
</template>

<script>
  import common from "./common/common";
  import MenuCell from "./MenuCell";


  export default {
    name: "MenuTable",
      components: {MenuCell},
      data: () => ({
        cells: common.cells
    }),
    methods: {
      clickCell(item) {
        console.log('menuTable');
        this.$emit('clickOnCell', item)
      }
    }
  }
</script>

<style lang="sass">
  .menuTable
    margin-top: -35px
    display: flex
    flex-direction: column
    background-image: url(FON.jpg)
    -moz-background-size: 100% /* Firefox 3.6+ */
    -webkit-background-size: 100% /* Safari 3.1+ и Chrome 4.0+ */
    -o-background-size: 100% /* Opera 9.6+ */
    background-size: 100% /* Современные браузеры */
    justify-content: center
    align-content: center
    position: relative
    &__file
      align-self: center
      font-weight: bold
      font-size: 42px
      color: yellow
      transition: color 0.2s
      &:hover
        color: #DBCB00
    &__title
      display: flex
      padding: 15px
      display: flex
      justify-content: center
      align-items: center
      color: white
      font-family: "BicubikRegular"
      font-size: 52px
      font-weight: bold
      -webkit-text-stroke: 1px #0FB609
      -webkit-filter: drop-shadow(2px 3px 2px black)
      filter: drop-shadow(2px 3px 2px black)
      > span
        margin-left: 20px
        line-height: 1
    &__items
      display: flex
      flex-wrap: wrap
      justify-content: center
      align-self: center
      .img-Imitatsia_brusa
        background-image: url(./menuIImg/Imitatsia_brusa.jpg)
        -moz-background-size: cover /* Firefox 3.6+ */
        -webkit-background-size: cover /* Safari 3.1+ и Chrome 4.0+ */
        -o-background-size: cover /* Opera 9.6+ */
        background-size: cover /* Современные браузеры */
      .img-Pogonazhnye_izdelia
        background-image: url(./menuIImg/Pogonazhnye_izdelia.jpg)
        -moz-background-size: cover /* Firefox 3.6+ */
        -webkit-background-size: cover /* Safari 3.1+ и Chrome 4.0+ */
        -o-background-size: cover /* Opera 9.6+ */
        background-size: cover /* Современные браузеры */
      .img-Vagonka
        background-image: url(./menuIImg/Vagonka.jpg)
        -moz-background-size: cover /* Firefox 3.6+ */
        -webkit-background-size: cover /* Safari 3.1+ и Chrome 4.0+ */
        -o-background-size: cover /* Opera 9.6+ */
        background-size: cover /* Современные браузеры */
      .img-Evrovagonka_shtil
        background-image: url(./menuIImg/Evrovagonka_shtil.jpg)
        -moz-background-size: cover /* Firefox 3.6+ */
        -webkit-background-size: cover /* Safari 3.1+ и Chrome 4.0+ */
        -o-background-size: cover /* Opera 9.6+ */
        background-size: cover /* Современные браузеры */
      .img-Doska_pola
        background-image: url(./menuIImg/Doska_pola.jpg)
        -moz-background-size: cover /* Firefox 3.6+ */
        -webkit-background-size: cover /* Safari 3.1+ и Chrome 4.0+ */
        -o-background-size: cover /* Opera 9.6+ */
        background-size: cover /* Современные браузеры */
      .img-Brusok
        background-image: url(./menuIImg/Brusok.jpg)
        -moz-background-size: cover /* Firefox 3.6+ */
        -webkit-background-size: cover /* Safari 3.1+ и Chrome 4.0+ */
        -o-background-size: cover /* Opera 9.6+ */
        background-size: cover /* Современные браузеры */
      .img-Mebelnii_shield
        background-image: url(./menuIImg/dee5f88573cccf3cab0635ba37cfee63.jpg)
        -moz-background-size: cover /* Firefox 3.6+ */
        -webkit-background-size: cover /* Safari 3.1+ и Chrome 4.0+ */
        -o-background-size: cover /* Opera 9.6+ */
        background-size: cover /* Современные браузеры */
      .img-Elementy_lestnitsy
        background-image: url(./menuIImg/Elementy_lestnitsy.jpg)
        -moz-background-size: cover /* Firefox 3.6+ */
        -webkit-background-size: cover /* Safari 3.1+ и Chrome 4.0+ */
        -o-background-size: cover /* Opera 9.6+ */
        background-size: cover /* Современные браузеры */
    &--adwords
      color: white
      font-size: 36px
      font-weight: bold
      width: 75%
      align-self: center
      text-align: center
      padding: 20px 5px
      border: 2px solid white
      margin: 10px
  @media only screen and (max-width: 512px)
    .menuTable
      margin-top: -20px
      border-radius: 10px
      &__title
        margin-left: unset
        > span
          font-size: 20px
          margin-left: 0px
      &--adwords
        font-size: 14px
  @media only screen and (orientation: landscape) and (max-width: 1024px) and (min-width: 400px)
    .menuTable
      &__title
        > span
          font-size: 26px
      &--adwords
        font-size: 14px
</style>
