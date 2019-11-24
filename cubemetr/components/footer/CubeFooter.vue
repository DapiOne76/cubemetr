<template>
  <div class="cubeFooter">
    <div class="cubeFooter__info">
      <div class="cubeFooter__info--img--wrapper" >
        <img class="cubeFooter__info--img" src="./meme.png">

      </div>
      <div class="cubeFooter__info--text">
        <span class="cubeFooter__info--header" v-text="'КАК НАС НАЙТИ'"></span>
        <div class="cubeFooter__info--block">
          <img height="28px" width="28px" src="./phone.png">
          <span class="cubeFooter__info--description" v-text="'Телефон:'"></span>
        </div>
        <a class="cubeFooter__info--number" href="tel:+74852334043">+7 (4852) 33 40 43</a>
        <a class="cubeFooter__info--number" href="tel:+74852332982">+7 (4852) 33 29 82</a>
        <div class="cubeFooter__info--block">
          <img height="28px" width="28px" src="./location.png">
          <span class="cubeFooter__info--description" v-text="'Схема проезда'"></span>
        </div>
        <span class="cubeFooter__info--explanation" v-text="'Адрес:'"></span>
        <span v-text="'ул. Промзона Декабристов, 2'"></span>
        <span class="cubeFooter__info--explanation"  v-text="'E-mail:'"></span>
        <span v-text="'patrikslava2015@yandex.ru'"></span>
      </div>
    </div>
    <div id="map"></div>
  </div>
</template>

<script>
  export default {
    name: "CubeFooter",
    data: () => ({
       map: null,
    }),
    methods: {
      init() {
        ymaps.ready(() => {
            this.map = new ymaps.Map("map", {
                center: [57.590957, 39.820349],
                zoom: 13
            });
            const myGeoObject = new ymaps.Placemark([57.590957, 39.820349], {}, {
                preset: 'islands#blueDotIcon'
            });
            this.map.geoObjects.add(myGeoObject);
        });
      }
    },
    created() {
        const yandexMapScript = document.createElement("script");
        yandexMapScript.setAttribute("src", "https://api-maps.yandex.ru/2.1/?apikey=a2382f4e-e3bc-44e6-8504-bee805288d9c&lang=ru_RU");
        yandexMapScript.addEventListener("load", this.init);
        document.head.appendChild(yandexMapScript);
    }
  }
</script>

<style lang="sass">
  .cubeFooter
    margin-top: -35px
    display: flex
    justify-content: center
    width: 100%
    height: 385px
    padding-top: 60px
    background-image: url(./footer.jpg)
    &__info
      display: flex
      margin-right: 35px
      &--img
        width: 325px
        height: 325px
      &--text
        display: flex
        flex-direction: column
        font-size: 20px
        color: white
        justify-content: center
      &--header
        color: #eaddb4
        font-size: 28px
        font-weight: bold
      &--block
        display: flex
        align-items: center
        > span
          margin-left: 10px
      &--description
        font-size: 24px
      &--number
        color: white
    #map
      width: 500px
      height: 300px
  @media only screen and (max-width: 640px)
    .cubeFooter
      flex-direction: column-reverse
      justify-content: flex-start
      align-items: center
      height: unset
      #map
        width: 350px
        height: 250px
      &__info
        flex-direction: row-reverse
        padding: 15px 0 15px
        margin-right: 0px
        &--img
          width: 130px
          height: 130px
        &--text
          font-size: 12px
        &--header
          font-size: 16px
        &--block
          > span
            margin-left: 10px
        &--description
          font-size: 14px
        &--explanation
          font-size: 16px
  @media only screen and (max-width: 640px)
    .cubeFooter
      #map
        width: 300px
        height: 200px
  @media only screen and (orientation: landscape) and (max-width: 1024px) and (min-width: 400px)
    .cubeFooter
      height: 300px
      #map
        width: 350px
        height: 250px
      &__info
        height: 250px
        align-items: center
        &--img
          width: 130px
          height: 130px
          margin-right: 10px
        &--text
          font-size: 12px
        &--header
          font-size: 16px
        &--block
          > span
            margin-left: 10px
        &--description
          font-size: 14px
        &--explanation
          font-size: 16px
</style>
