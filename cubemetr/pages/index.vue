<template>
  <div class="cubemetr--wrapper">
    <div class="cubemetr">
      <cube-header/>
      <img class="cubemetr--img" src="./25-sosna.png">
      <menu-table/>
      <client-only>
        <cube-footer/>
      </client-only>
    </div>
    <div class="cubemetr--wrapper__absolute">
      <div class="cubemetr--wrapper__header"></div>
      <div class="cubemetr--wrapper__img"></div>
      <div class="cubemetr--wrapper__menu"></div>
      <div class="cubemetr--wrapper__footer"></div>
    </div>
  </div>
</template>

<script>

import CubeHeader from "../components/header/CubeHeader";
import MenuTable from "../components/menu/MenuTable";
import CubeFooter from "../components/footer/CubeFooter";
export default {
    components: {CubeFooter, MenuTable, CubeHeader},
}
</script>

<style lang="sass">
  @font-face
    font-family: "BicubikRegular"
    src: url("../components/fonts/BicubikRegular/BicubikRegular.eot")
    src: url("../components/fonts/BicubikRegular/BicubikRegular.eot?#iefix")format("embedded-opentype"),
    url("../components/fonts/BicubikRegular/BicubikRegular.woff") format("woff"),
    url("../components/fonts/BicubikRegular/BicubikRegular.ttf") format("truetype")
    font-style: normal
    font-weight: normal
  .cubemetr
    display: flex
    flex-direction: column
    align-self: center
    max-width: 1280px
    flex-basis: 100%
    -webkit-filter: drop-shadow(0px 0px 60px black)
    filter: drop-shadow(0px 0px 60px black)
    &--wrapper
      display: flex
      justify-content: center
      position: relative
      &__absolute
        position: absolute
        z-index: -999999
        display: flex
        flex-direction: column
        width: 100%
        height: 100%
        -webkit-filter: blur(10px)
        filter: blur(10px)
      &__header
        width: 100%
        background-image: url(../components/header/FON_ShAPKA_Clear.jpg)
        -moz-background-size: 100% /* Firefox 3.6+ */
        -webkit-background-size: 100% /* Safari 3.1+ и Chrome 4.0+ */
        -o-background-size: 100% /* Opera 9.6+ */
        background-size: 100% /* Современные браузеры */
        background-repeat: no-repeat
        height: 700px
      &__img
        background-image: url(./25-sosna.png)
        -moz-background-size: 100% /* Firefox 3.6+ */
        -webkit-background-size: 100% /* Safari 3.1+ и Chrome 4.0+ */
        -o-background-size: 100% /* Opera 9.6+ */
        background-size: 100% /* Современные браузеры */
        background-repeat: no-repeat
        width: 100%
        height: 398px
      &__menu
        background-image: url(../components/menu/FON.jpg)
        -moz-background-size: 100% /* Firefox 3.6+ */
        -webkit-background-size: 100% /* Safari 3.1+ и Chrome 4.0+ */
        -o-background-size: 100% /* Opera 9.6+ */
        background-size: 100% /* Современные браузеры */
        flex: 1
        width: 100%
      &__footer
        background-image: url(../components/footer/footer.jpg)
        -moz-background-size: 100% /* Firefox 3.6+ */
        -webkit-background-size: 100% /* Safari 3.1+ и Chrome 4.0+ */
        -o-background-size: 100% /* Opera 9.6+ */
        background-size: 100% /* Современные браузеры */
        background-repeat: no-repeat
        width: 100%
        height: 415px
    &--img
      width: 100%
      height: 433px
</style>

