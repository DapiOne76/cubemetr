<template>
  <div @click="clickCell" class="menuCell">
    <img :class="srcImg">
    <span v-text="item.name"></span>
  </div>
</template>

<script>
  export default {
    name: "MenuCell",
    props: {
        item: {}
    },
    computed: {
        srcImg() {
            return `menuCell__img img-${this.item.src}`
        }
    },
    methods: {
      clickCell() {
        console.log('menuCell');
        this.$emit('clickOnCell', this.item)
      }
    }
  }
</script>

<style lang="sass">
  .menuCell
    display: flex
    position: relative
    width: 520px
    color: white
    border: 7px solid #0FB609
    border-radius: 25px
    margin: 20px
    height: 325px
    justify-content: flex-end
    transition: filter 150ms
    &:before
      content: ''
      position: absolute
      width: 100%
      height: 100%
      background-color: black
      transition: opacity 150ms
      opacity: 0
      border-radius: 20px
      z-index: 5
    &:hover
      -webkit-filter: drop-shadow(0px 0px 15px black)
      filter: drop-shadow(0px 0px 15px black)
      &:before
        opacity: 0.15
    > span
      padding: 0 10px 10px 0
      align-self: flex-end
      border-bottom-left-radius: 25px
      border-bottom-right-radius: 25px
      font-size: 48px
      flex-basis: 100%
      text-align: right
      z-index: 1
      background-color: rgba(210, 105, 30, 0.5)
      &:last-child
        padding-left: 15px
    &__img
      position: absolute
      width: 100%
      height: 100%
      background-repeat: no-repeat
      border-radius: 20px

  @media only screen and (max-width: 640px)
    .menuCell
      width: 300px
      height: 175px
      > span
        font-size: 24px
  @media only screen and (orientation: landscape) and (max-width: 1024px) and (min-width: 400px)
    .menuCell
      width: 300px
      height: 175px
      > span
        font-size: 24px
</style>
