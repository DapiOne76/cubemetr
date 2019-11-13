<template>
  <div class="header">
    <div class="header__wrapper">
      <span class="header__name" v-text="'КУБОМЕТР'"></span>
      <span class="header__name--description" v-text="'ПРОДАЖА СУХОГО СТРОГАННОГО ПИЛОМАТЕРИАЛА'"></span>
      <div class="header__time--number__wrapper">
        <div class="header__watch">
          <div class="header__watch--image">
          </div>
          <div class="header__watch--description">
            <span v-text="'пн-пт: с 9:00-18:00'"></span>
            <span v-text="'сб: с 9:00-15:00'"></span>
          </div>
        </div>
        <div class="header__number">
          <span v-text="'8-908-027-07-54'"></span>
        </div>
      </div>
      <span class="header__address" v-text="'АДРЕС: УЛ.РАСТОРГУЕВА 20 А'"></span>
    </div>
  </div>
</template>

<script>
  export default {
      name: "CubeHeader"
  }
</script>

<style lang="sass">
  .header
    background-image: url(FON_ShAPKA.jpg)
    -moz-background-size: 100% /* Firefox 3.6+ */
    -webkit-background-size: 100% /* Safari 3.1+ и Chrome 4.0+ */
    -o-background-size: 100% /* Opera 9.6+ */
    background-size: 100% /* Современные браузеры */
    display: flex
    width: 100%
    height: 978px
    color: white
    font-family: "BicubikRegular"
    &__wrapper
      width: 100%
      display: flex
      flex-direction: column
      justify-content: flex-end
    &__name
      -webkit-filter: drop-shadow(-19px 15px 2px black)
      filter: drop-shadow(-19px 15px 2px black)
      font-size: 168px
      padding-left: 10%
      font-style: italic
      text-shadow: #00ca00 0px 0px 12px, #006f3a 0px 0px 16px
      line-height: 1
      margin-bottom: 10px
    &__name--description
      -webkit-filter: drop-shadow(-19px 15px 2px black)
      filter: drop-shadow(-19px 15px 2px black)
      font-style: italic
      font-size: 42px
      padding-left: 19%
      font-weight: bold
      margin-bottom: 65px
    &__time--number__wrapper
      display: flex
      padding-left: 5%
      margin-bottom: 35px
    &__watch
      display: flex
      &--image
        background-image: url(watch.png)
        -moz-background-size: 100% /* Firefox 3.6+ */
        -webkit-background-size: 100% /* Safari 3.1+ и Chrome 4.0+ */
        -o-background-size: 100% /* Opera 9.6+ */
        background-size: 100% /* Современные браузеры */
        height: 140px
        width: 140px
        z-index: 2
        -webkit-filter: drop-shadow(-19px 15px 2px black)
        filter: drop-shadow(-19px 15px 2px black)
      &--description
        -webkit-filter: drop-shadow(-19px 15px 2px black)
        filter: drop-shadow(-19px 15px 2px black)
        display: flex
        flex-direction: column
        justify-content: center
        font-size: 48px
        text-shadow: #00ca00 0px 0px 2px, #006f3a 0px 0px 3px
    &__number
      margin-left: 30px
      width: 680px
      height: 140px
      position: relative
      display: flex
      justify-content: center
      align-items: center
      &::before
        z-index: 1
        content: ""
        position: absolute
        width: 100%
        height: 100%
        background-image: url(table.png)
        background-repeat: no-repeat
        -moz-background-size: 100% /* Firefox 3.6+ */
        -webkit-background-size: 100% /* Safari 3.1+ и Chrome 4.0+ */
        -o-background-size: 100% /* Opera 9.6+ */
        background-size: 100% /* Современные браузеры */
        -webkit-transform: scaleX(-1)
        -moz-transform: scaleX(-1)
        -ms-transform: scaleX(-1)
        -o-transform: scaleX(-1)
        transform: scaleX(-1)
        -webkit-filter: drop-shadow(10px 9px 9px black)
        filter: drop-shadow(10px 9px 9px black)
      > span
        font-size: 58px
        z-index: 2
        text-shadow: #00ca00 0px 0px 4px, #006f3a 0px 0px 7px
        -webkit-filter: drop-shadow(-19px 15px 2px black)
        filter: drop-shadow(-19px 15px 2px black)
    &__address
      -webkit-filter: drop-shadow(-19px 15px 2px black)
      filter: drop-shadow(-19px 15px 2px black)
      font-size: 72px
      align-self: center
      text-shadow: #00ca00 0px 0px 4px, #006f3a 0px 0px 7px
</style>
