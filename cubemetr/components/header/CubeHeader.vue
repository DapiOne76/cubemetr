<template>
  <div class="header">
    <div class="header__wrapper">
      <span class="header__name--description" v-text="'ПРОДАЖА СУХОГО СТРОГАННОГО ПИЛОМАТЕРИАЛА'"></span>
      <div class="header__time--number__wrapper">
        <div class="header__watch">
          <div class="header__watch--description">
            <span v-text="'пн-пт: с 9:00-18:00'"></span>
            <span v-text="'сб: с 9:00-15:00'"></span>
          </div>
        </div>
        <div class="header__number">
          <span v-text="'8-908-027-07-43'"></span>
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
    background-repeat: no-repeat
    display: flex
    width: 100%
    height: 700px
    color: white
    flex-direction: column
    justify-content: flex-end
    font-family: "BicubikRegular"
    &__wrapper
      width: 100%
      display: flex
      flex-direction: column
      justify-content: flex-end
    &__name--description
      font-style: italic
      font-size: 28px
      padding-left: 19%
      font-weight: bold
      margin-bottom: 65px
    &__time--number__wrapper
      display: flex
      justify-content: space-between
      margin-bottom: 31px
      padding-right: 5%
    &__watch
      display: flex
      &--description
        display: flex
        flex-direction: column
        justify-content: center
        font-family: Arial
        font-size: 45px
        margin-left: 150px
        text-shadow: #00ca00 0px 0px 2px, #006f3a 0px 0px 3px
    &__number
      position: relative
      display: flex
      justify-content: center
      align-items: center
      padding-right: 20px
      -webkit-text-stroke: 1px #00ca00
      > span
        font-size: 47px
        z-index: 2
        font-weight: bold
        padding-top: 5px
    &__address
      font-size: 46px
      align-self: center
      text-shadow: #00ca00 0px 0px 4px, #006f3a 0px 0px 7px
  @media only screen and (max-width: 512px)
    .header
      height: unset
      &__name
        font-size: 38px
      &__name--description
        font-size: 16px
        margin-bottom: unset
        padding-left: 15%
      &__watch
        &--image
          width: 82px
          height: 82px
        &--description
          font-size: 11px
      &__number
        width: 160px
        height: 25px
        align-self: center
        > span
          font-size: 10px
      &__time--number__wrapper
        margin-bottom: unset
      &__address
        font-size: 18px
  @media only screen and (max-width: 340px)
    .header
      height: unset
      &__name
        font-size: 32px
      &__name--description
        font-size: 14px
        margin-bottom: unset
        padding-left: 12%
      &__watch
        &--image
          width: 82px
          height: 82px
        &--description
          font-size: 10px
      &__number
        width: 160px
        height: 25px
        align-self: center
        > span
          font-size: 9px
      &__time--number__wrapper
        margin-bottom: unset
      &__address
        font-size: 14px
  @media only screen and (orientation: landscape) and (max-width: 1024px) and (min-width: 400px)
    .header
      height: 350px
      &__name
        font-size: 42px
      &__name--description
        font-size: 18px
        margin-bottom: unset
        padding-left: 12%
      &__watch
        &--image
          width: 82px
          height: 82px
        &--description
          font-size: 10px
      &__number
        width: 160px
        height: 35px
        align-self: center
        > span
          font-size: 9px
      &__time--number__wrapper
        margin-bottom: unset
      &__address
        font-size: 14px
</style>
