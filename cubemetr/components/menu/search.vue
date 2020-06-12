<template>
  <div :class="`search ${focus ? 'focus' : ''}`">
    <input class="search-input" @focusin="setFocus" @focusout="disableFocus" placeholder="Поиск по названию" v-model="value" @keyup="change"/>
  </div>
</template>

<script>
  export default {
    name: "search",
    data: () => ({
      value: '',
      focus: false
    }),
    methods: {
      change() {
        this.$emit('change', this.value);
      },
      setFocus() {
        this.focus = true;
      },
      disableFocus() {
        this.focus = false;
      }
    }
  }
</script>

<style lang="less">
  @import "../../pages/consts";
.search {
  position: relative;
  &-input {
    border: transparent;
    width: 375px;
    height: 40px;
    font-size: 26px;
    outline:none;
  }
  &:after {
    content: "";
    background: @color-yellow;
    position: absolute;
    transition: width .5s;
    bottom: 0;
    left: 0;
    height: 2px;
    width: 20%;
  }
  &.focus {
    &:after {
      width: 100%;
    }
  }
}
  @media only screen and (max-width: 875px) {
    .search {
      align-self: center;
      width: 80%;
      &-input {
        width: 100%
      }
    }
  }
</style>
