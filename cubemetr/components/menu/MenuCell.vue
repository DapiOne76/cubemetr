<template>
  <div class="menuCell">
    <span v-text="item.name"></span>
  </div>
</template>

<script>
  export default {
    name: "MenuCell",
    props: {
        item: {}
    }
  }
</script>

<style lang="sass">
  .menuCell
    display: flex
    width: 600px
    color: black
    background-color: white
    border: 5px solid green
    border-radius: 15px
    margin: 3%
    height: 350px
    justify-content: flex-end
    > span
      padding: 0 10px 10px 0
      align-self: flex-end
      font-size: 48px
      flex-basis: 77%
      text-align: right
</style>
