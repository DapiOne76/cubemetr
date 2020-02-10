<template>
  <div class="advertising">
    <img :src="advertising">
  </div>
</template>

<script>
    export default {
        name: "advertising",
        props:[
          'advertising'
        ]
    }
</script>

<style lang="scss">
.advertising {
  display: flex;
  justify-content: center;
  > img {
    width: auto;
    height: auto;
  }
}
</style>
