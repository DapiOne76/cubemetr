<template>
  <div class="cubemetr">
    <cube-header/>
    <menu-table/>
    <client-only>
      <cube-footer/>
    </client-only>
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
    flex-basis: 100%
</style>

