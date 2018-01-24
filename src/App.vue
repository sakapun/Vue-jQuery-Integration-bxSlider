<template>
  <div>
    <div id="banner_slider">
      <div v-for="banner in banners">
        <img v-bind:alt="banner.name" v-bind:src="banner.url">
      </div>
    </div>
  </div>
</template>

<script>
  import $ from "jquery"
  global.jQuery = $;
  window.jQuery = $;
  require("bxslider");

  export default {
    name: "index-component",
    mounted() {
      // トップスライダー
      $(function () {
        $("#banner_slider").bxSlider({
          auto: true,             // 自動スライド
          infiniteLoop: true,     // 無限ループ
          pager: false,           // ページャー非表示
          autoHover: true,        // マウスオーバー時に自動遷移を停止
        });
      })
    },
    data() {
      return {
        banners: [{
          name: "ee",
          url: "https://camo.mybb.com/e01de90be6012adc1b1701dba899491a9348ae79/687474703a2f2f7777772e6a71756572797363726970742e6e65742f696d616765732f53696d706c6573742d526573706f6e736976652d6a51756572792d496d6167652d4c69676874626f782d506c7567696e2d73696d706c652d6c69676874626f782e6a7067"
        }, {
          name: "ee",
          url: "https://demo.phpgang.com/crop-images/demo_files/pool.jpg"
        }]
      }
    }

  }
</script>

<style scoped>

</style>