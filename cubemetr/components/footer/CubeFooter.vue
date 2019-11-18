<template>
  <div class="cubeFooter">
    <div class="cubeFooter__info">
      <img height="325px" width="325px" src="./meme.png">
      <div class="cubeFooter__info--text">
        <span class="cubeFooter__info--header" v-text="'КАК НАС НАЙТИ'"></span>
        <div class="cubeFooter__info--block">
          <img height="28px" width="28px" src="./phone.png">
          <span class="cubeFooter__info--description" v-text="'Телефон:'"></span>
        </div>
        <span class="cubeFooter__info--number" v-text="'+7 (4852) 33 40 43'"></span>
        <span class="cubeFooter__info--number" v-text="'+7 (4852) 33 29 82'"></span>
        <div class="cubeFooter__info--block">
          <img height="28px" width="28px" src="./location.png">
          <span class="cubeFooter__info--description" v-text="'Схема проезда'"></span>
        </div>
        <span v-text="'Адрес:'"></span>
        <span v-text="'ул. Промзона Декабристов, 2'"></span>
        <span v-text="'E-mail:'"></span>
        <span v-text="'patrikslava2015@yandex.ru'"></span>
      </div>
    </div>
    <div id="map" style="width: 500px; height: 300px"></div>
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
    display: flex
    width: 100%
    height: 350px
    padding-top: 25px
    background-image: url(./footer.jpg)
    padding-left: 15%
    &__info
      display: flex
      margin-right: 35px
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
</style>
