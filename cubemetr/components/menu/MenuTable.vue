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
                name: 'ИМИТАЦИЯ БРУСА',
                src: 'Imitatsia_brusa'
            },
            {
                name: 'ПОГОНАЖНЫЕ ИЗДЕЛИЯ',
                src: 'Pogonazhnye_izdelia'

            },
            {
                name: 'ЕВРОВАГОНКА',
                src: 'Vagonka'
            },
            {
                name: 'ВАГОНКА ШТИЛЬ',
                src: 'Evrovagonka_shtil'
            },
            {
                name: 'ДОСКА ПОЛА',
                src: 'Doska_pola'
            },
            {
                name: 'БРУСОК',
                src: 'Brusok'
            },
            {
                name: 'БЛОК ХАУС',
                src: 'Blok_khaus'
            },
            {
                name: 'ЭЛЕТЕМЕНТЫ ЛЕСТНИЦ',
                src: 'Elementy_lestnitsy'
            },
        ]
    })
  }
</script>

<style lang="sass">
  .menuTable
    margin-top: -35px
    border-radius: 35px
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
      .img-Blok_khaus
        background-image: url(./menuIImg/Blok_khaus.jpg)
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
  @media only screen and (max-width: 512px)
    .menuTable
      margin-top: -20px
      border-radius: 10px
      &__title
        margin-left: unset
        > span
          font-size: 20px
          margin-left: 0px
  @media only screen and (orientation: landscape) and (max-width: 1024px) and (min-width: 400px)
    .menuTable
      &__title
        > span
          font-size: 26px
</style>
