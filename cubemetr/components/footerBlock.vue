<template>
  <div class="footerBlock c-flex-column">
    <div class="footerBlock-info c-flex">
      <div id="map"></div>
      <div class="footerBlock-info_text">
        <h2 class="footerBlock-info_text-1">Магазин</h2>
        <h2 class="footerBlock-info_text-2">КУБОМЕТР</h2>
        <div class="footerBlock-phone c-flex-align-items-center">
          <span>📱</span>
          <a
            :href="`tel:${'+7 908 027-07-43'.replace(/\s|-/g, '')}`">
            +7 908 027-07-43
          </a>
        </div>
        <div class="footerBlock-mapInfo c-flex c-flex-align-items-center">
          <div class="icon pe-7s-map-marker">
          </div>
          <div class="footerBlock-mapInfo_block c-flex-column">
            <span>г. Рыбинск,</span>
            <span>ул.Волжская Набережная 163</span>
            <span>(вход со стороны набережной)</span>
          </div>
        </div>
        <div class="footerBlock-mapInfo c-flex c-flex-align-items-center">
          <div class="icon pe-7s-clock">
          </div>
          <div class="footerBlock-mapInfo_block c-flex-column">
            <span>ПН-ПТ: 09:00 — 18:00</span>
            <span>ОБЕД:  13:00 - 14:00</span>
            <span>СБ-ВС: ВЫХОДНОЙ</span>
          </div>
        </div>
      </div>
    </div>
    <div class="footerBlock-otzvon c-flex">
      <div class="footerBlock-question c-flex-column c-flex-justify-content-center ">
        <h2>
          Закажи бытовку себе на участок!
        </h2>
        <h2>
          <a href="https://domoy76.ru"> ПЕРЕЙТИ НА САЙТ ООО "ДОМОЙ"</a>
        </h2>
      </div>
      <div class="footerBlock-number c-flex-justify-content-center c-flex-align-items-center">
        <img :src="domoy">
      </div>
    </div>
    <span class="footerBlock--OOO">Информация на сайте не является публичной офертой.   Все права защищены.</span>
  </div>
</template>

<script>
  import domoy from './d315fbc.jpg'

  export default {
    name: "footerBlock",
    data: () => ({
      number: '+7 908 027-07-43',
      map: null,
      domoy
    }),
    methods: {
      init() {
        ymaps.ready(() => {
          this.map = new ymaps.Map("map", {
            center: [58.052242, 38.839894],
            zoom: 13
          });
          const myGeoObject = new ymaps.Placemark([58.052242, 38.839894], {}, {
            preset: 'islands#blueDotIcon'
          });
          this.map.geoObjects.add(myGeoObject);
        });
      }
    },
    created() {
      const yandexMapScript = document.createElement("script");
      yandexMapScript.setAttribute("src", "https://api-maps.yandex.ru/2.1.68?apikey=a2382f4e-e3bc-44e6-8504-bee805288d9c&lang=ru_RU");
      yandexMapScript.addEventListener("load", this.init);
      document.head.appendChild(yandexMapScript);
    }
  }
</script>

<style lang="less">
  @-webkit-keyframes pulse {
    0% {
      -webkit-box-shadow: 0 0 0 0 rgba(1, 71, 127, 0.4);
    }
    20% {
      -webkit-box-shadow: 0 0 0 5px rgba(1, 71, 127, 0.2);
    }
    60% {
      -webkit-box-shadow: 0 0 0 15px rgba(12, 96, 53, 0.1);
    }
    70% {
      -webkit-box-shadow: 0 0 0 12px rgba(12, 96, 53, 0.1);
    }
    100% {
      -webkit-box-shadow: 0 0 0 0 rgba(13, 165, 100, 0);
    }
  }
  @keyframes pulse {
    0% {
      -moz-box-shadow: 0 0 0 0 rgba(1, 71, 127, 0.4);
      box-shadow: 0 0 0 0 rgba(1, 71, 127, 0.4);
    }
    20% {
      -moz-box-shadow: 0 0 0 5px rgba(1, 71, 127, 0.2);
      box-shadow: 0 0 0 5px rgba(1, 71, 127, 0.2);
    }
    60% {
      -moz-box-shadow: 0 0 0 15px rgba(12, 96, 53, 0.1);
      box-shadow: 0 0 0 15px rgba(12, 96, 53, 0);
    }
    70% {
      -moz-box-shadow: 0 0 0 12px rgba(12, 96, 53, 0.1);
      box-shadow: 0 0 0 12px rgba(12, 96, 53, 0);
    }
    100% {
      -moz-box-shadow: 0 0 0 30px rgba(13, 165, 100, 0);
      box-shadow: 0 0 0 30px rgba(13, 165, 100, 0);
    }
  }
  @import "pages/consts";
  #map {
    width: 700px;
    height: 500px;
  }

  .footerBlock {
    position: relative;
    &--OOO {
      position: absolute;
      left: 25px;
      bottom: 5px;
      white-space: pre-wrap;
      @media only screen and (max-width: 875px) {
        font-size: 5px;
      }
    }
    &-phone {
      font-size: 30px;
      margin: 25px 0 15px;
      a {
        margin-left: 20px;
        text-decoration: none;
        font-family: sans-serif;
        color: @color-yellow;
        -webkit-transition: color .3s;
        transition: color .3s;
        font-size: 22px;
        &:hover {
          color: black;
        }
      }
    }
    &-mapInfo {
      padding: 25px 0;
      border-top: 1px dashed #444444;
      white-space: pre-wrap;
      color: #444444;
      span {
        margin: 5px 0;
        font-family: sans-serif;
        font-weight: 400;
        font-style: normal;
        font-size: 16px;
      }
      .icon {
        font-size: 30px;
        line-height: 30px;
      }
      &_block {
        padding-left: 20px;
      }
    }
    &-info {
      margin-left: 10%;
      background-color: hsla(0,0%,96.1%,.85);
      margin-right: 10%;
      &_text {
        padding-left: 30px;
        padding-top: 25px;
      }
      &_text-1,
      &_text-2 {
        font-size: 56px;
        margin: 0;
      }
      &_text-1 {
        color: #01477f;
      }
      &_text-2 {
        color: @color-yellow;
      }
    }
    &-otzvon {
      height: 221px;
    }
    &-question {
      flex-basis: 60%;
      background-color: #ffd13b;
      color: black;
      padding-left: 120px;
      padding-right: 60px;
      h2:first-child,
      h2:last-child {
        font-size: 30px;
        text-align: left;
        margin: 0;
      }
      h2:first-child {
        font-weight: 300;
      }
      h2:last-child {
        a {
          color: black;
        }
        text-decoration: underline;
        font-weight: bold;
        text-transform: uppercase;
      }
    }
    &-number {
      position: relative;
      background-color: @color-yellow;
      flex-basis: 40%;
      img {
        width: 90%;
        height: 90%;
        border-radius: 15px;
        @media only screen and (max-width: 875px) {
          height: 70%;
          width: 100%;
          margin-right: 10px;
        }
      }
      &:before {
        content: '';
        position: absolute;
        border-color: transparent @color-yellow;
        border-style: solid;
        border-width: 110px 40px 110px 0px;
        left: -40px;
        height: 0px;
        width: 0px;
      }
      a {
        padding: 16px 40px;
        transition: color .4s, background-color .4s;
        color: #666;
        border: 1px solid #01477f;
        text-decoration: none;
        &:hover {
          animation: pulse 2s;
          color: @color-yellow;
          background-color: #01477f;
        }
      }
    }
  }
  @media only screen and (max-width: 875px) {
    .footerBlock {
      &-info {
        -webkit-box-orient: vertical;
        -webkit-box-direction: normal;
        flex-direction: column;
        margin-left: 0;
        margin-right: 0;
        #map {
          width: 100%;
          height: 200px;
        }
        &_text {
          padding-left: 0;
        }
      }
      &-otzvon {
        height: 120px;
      }
      &-question {
        flex-basis: 50%;
        padding-left: 15px;
        h2:first-child,
        h2:last-child {
          font-size: 13px;
          text-align: left;
          margin: 0;
        }
      }
      &-number {
        flex-basis: 50%;
        a {
          font-size: 13px;
          padding: 16px 16px;
        }
        &:before {
          border-width: 60px 40px 60px 0px;
        }
      }
    }
  }
</style>
