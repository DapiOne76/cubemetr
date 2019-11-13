<template>
  <div class="cubemetr">
    <cube-header/>
  </div>
</template>

<script>

import CubeHeader from "../components/header/CubeHeader";
export default {
    components: {CubeHeader}
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
    font-weight: normal;

</style>

