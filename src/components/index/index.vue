<template>
  <div class="index_container">
    <!--{{goods}}-->
    <index-header></index-header>
    <index-carousel></index-carousel>
    <index-category></index-category>
    <index-buys></index-buys>
    <div class="index_discount">
      <div class="discount_img" v-if="goods[6]">
        <img :src="goods[6].content_images[0][0].image">
      </div>
    </div>
    <!--recommend组件-->
    <div class="index_recommend clearfix">
      <div class="recommend_imgR f_l">
        <img :src="goods[8].content_images[0][0].image" alt="">
      </div>
      <div class="hr"></div>
      <div class="recommend_imgL f_r">
        <div class="img1"><img :src="goods[8].content_images[1][0].image" alt=""></div>
        <div class="hr"></div>
        <div class="img2 clearfix"><img :src="goods[8].content_images[1][1].image" alt=""></div>
      </div>
    </div>
    <!--sale组件-->
    <!--<div class="index_sale">
      <div class="sale_top">
        <i class="img_left"></i>
        <i class="img_right"></i>
      </div>
      &lt;!&ndash;{{goods[13].content_images[0][0].image}}&ndash;&gt;
      <div class="sale_list">
        <img :src="goods[13].content_images[0][0].image" alt="">
      </div>
      <div class="sale_list">
        <img :src="goods[15].content_images[0][0].image" alt="">
      </div>
      <div class="sale_list">
        <img :src="goods[17].content_images[0][0].image" alt="">
      </div>
      <div class="sale_list">
        <img :src="goods[19].content_images[0][0].image" alt="">
      </div>
      <div class="sale_list">
        <img :src="goods[21].content_images[0][0].image" alt="">
      </div>
      <div class="sale_list">
        <img :src="goods[23].content_images[0][0].image" alt="">
      </div>
      <div class="sale_list">
        <img :src="goods[25].content_images[0][0].image" alt="">
      </div>
    </div>-->
    <!--体验馆组件-->
    <index-experience></index-experience>
    <!--<div class="index_experience_hall adorable_pet">-->
      <!--<i class="play"></i>-->
      <!--<div class="experience_hall_top adorable_pet_top">-->
        <!--<i class="img_left"></i>-->
        <!--<i class="img_right"></i>-->
      <!--</div>-->
      <!--&lt;!&ndash;{{goods[32].value} [{}]}//需要遍历&ndash;&gt;-->
      <!--<div class="sale_list adorable_pet_list" v-for="item in goods[37].value">-->
        <!--<img :src="item.cover.image" alt="">-->
      <!--</div>-->
      <!--<div v-for="item in goods[37].value">-->
        <!--<div class="adorable_pet_text">{{item.share_target.param.title}}</div>-->
        <!--<div class="adorable_pet_look"><i>观看数</i><i></i><i>{{item.visit}}</i></div>-->
      <!--</div>-->
    <!--</div>-->
    <!--小剧场 video-->
    <!--<div class="index_experience_hall adorable_pet Theatre">-->
      <!--<i class="play"></i>-->
      <!--<div class="experience_hall_top adorable_pet_top Theatre_top">-->
        <!--<i class="img_left"></i>-->
        <!--<i class="img_right"></i>-->
      <!--</div>-->
      <!--<div class="sale_list adorable_pet_list" v-for="item in goods[40].value">-->
        <!--<img :src="item.cover.image" alt="">-->
      <!--</div>-->
      <!--<div v-for="item in goods[40].value">-->
        <!--<div class="adorable_pet_text">{{item.share_target.param.title}}</div>-->
        <!--<div class="adorable_pet_look"><i>观看数</i><i></i><i>{{item.visit}}</i></div>-->
      <!--</div>-->
    <!--</div>-->
    <!--留白-->
    <div class="while"></div>
  </div>
</template>
<script>
  import {mapState} from 'vuex'
  import IndexHeader from 'page/index/index-header/index-header'
  import IndexCarousel from 'page/index/index-carousel/index-carousel'
  import IndexCategory from 'page/index/index-category/index-category'
  import IndexExperience from 'page/index/index-experience/index-experience'
  import IndexBuys from 'page/index/index-buys/index-buys'

  export default {
    /*计算属性 取出来ajax获取的数据*/
    mounted() {
      this.$store.dispatch('reqGoods')
    },
    computed: {
      ...mapState(['goods'])
    },
    methods: {
      /*跳转到search路由组件*/
      search() {
        this.$router.push('/search');
      }
    },
    components: {
      IndexHeader,
      IndexCarousel,
      IndexCategory,
      IndexExperience,
      IndexBuys
    }
  }
</script>
<style lang="less">
  @import "~common/css/public";

  @rem: 750/16rem;
  .index_container {
    width: 100%;
    background: #F3F4F6;
    /*head-part*/
    .index_head {
      width: 100%;
      height: 190/@rem;
      position: relative;
      .head_top {
        width: 100%;
        height: 70/@rem;
        margin-top: 0/@rem;
        position: relative;
        input {
          padding: 10/@rem 0;
          margin-left: 15/@rem;
          border-radius: 10/@rem;
          background: #E9E9E9;
          color: #000000;
          width: 439/@rem;
          padding-left: 24/@rem;
        }
        span {
          color: #908B8D;
          font-size: 28/@rem;
          font-weight: 600;
        }
        .span1 {
          margin-left: 20/@rem;
        }
        .span2 {
          position: absolute;
          top: 15/@rem;
          left: 110/@rem;
          height: 45/@rem;
          width: 1px;
          background: rgba(144, 139, 141, .4);;
        }
        .search_img {
          position: absolute;
          top: 30/@rem;
          right: 118/@rem;
          display: inline-block;
          width: 24/@rem;
          height: 24/@rem;
          background-image: url("./search.png");
          background-repeat: no-repeat;
          background-size: cover;
        }
        .chat_img {
          display: inline-block;
          position: absolute;
          top: 20/@rem;
          right: 30/@rem;
          width: 40/@rem;
          height: 40/@rem;
          background-image: url("./chat.png");
          background-repeat: no-repeat;
          background-size: cover;
        }
      }
      .head_bottom {
        width: 100%;
        margin-top: 40/@rem;
        overflow: hidden;
        .bottom_ul {
          width: 144%;
          display: flex;
          text-align: center;
          padding-right: 40/@rem;
          li {
            flex: 1;
            float: left;
            a {
              display: inline-block;
              font-size: 28/@rem;
              font-weight: 600;
              color: #706D73;
            }
            .current {
              color: #389C42;
              border-bottom: 2px solid #389C42;;
            }
          }
        }
      }
      .hr {
        width: 684/@rem;
        height: 1px;
        position: absolute;
        background: rgba(112, 109, 115, .5);
        bottom: 0;
        left: 46/@rem;
      }
    }
    /*轮播部分*/
    .index_carousel {
      width: 100%;
      overflow: hidden;
      background: #ffffff;
      /*索引定位*/
      position: relative;
      .index_carousel_images {
        /*4倍宽度  横向 四张图片*/
        width: 100%;
        /*-webkit-transform: translateX(-16.667%);
        transform: translateX(-16.667%);*/
        li {
          float: left;
          width: 16.6667%;
          a {
            display: block;
            width: 100%;
            img {
              display: block;
              width: 100%;
            }
          }
        }
      }
      /*小图标*/
      .index_carousel {
        position: absolute;
        bottom: 30/@rem;
        left: 50%;
        margin-left: -20/@rem;
        background: rgba(255, 255, 255, 0.1);
        li {
          float: left;
          width: 10/@rem;
          height: 10/@rem;
          border-radius: 50%;
          border: 1px solid white;
          margin-left: 5/@rem;
        }
        .current {
          background-color: deeppink
        }
      }
    }
    /*category部分*/
    .index_category {
      width: 100%;
      height: 366/@rem;
      background: #ffffff;
      .category_1 {
        width: 100%;
        margin-top: 0/@rem;
        ul {
          width: 100%;
          text-align: center;
          li {
            float: left;
            a {
              img {
                width: 145/@rem;
              }
            }
          }
        }
      }
    }
    /*秒杀组件*/
    .index_P_buying {
      width: 100%;
      height: 400/@rem;
      position: relative;
      background: #ffffff;
      .P_buying_top {
        width: 100%;
        margin-top: 30/@rem;
        .img_left {
          margin: 28/@rem 0 0 0;;
          position: absolute;
          top: 0;
          left: -25/@rem;
          width: 230/@rem;
          height: 60/@rem;
          background-image: url("./suprice.png");
          background-repeat: no-repeat;
          background-size: cover;
        }
        text-align: center;
        line-height: 90/@rem;
        .Seckill {
          display: block;
          position: relative;
          font-size: 28/@rem;
          margin-left: -100/@rem;
          /*i{
            font-style: normal;
            border: 1px solid #A7A7A5;
            padding: 5/@rem 5/@rem 5/@rem 5/@rem;
          }*/
          ul {
            width: 149/@rem;
            position: absolute;
            left: 525/@rem;
            top: 19/@rem;
            line-height: 50/@rem;
            background: #A2EE7C;
            border-radius: 10/@rem;
            padding-left: 20/@rem;
            box-shadow: 1px 1px #33DA82;
            li {
              height: 50/@rem;
              float: left;
            }
          }
        }
        .img_right {
          position: absolute;
          top: 34/@rem;
          right: 32/@rem;
          width: 100/@rem;
          height: 50/@rem;
          background-image: url("./more1.png");
          background-repeat: no-repeat;
          background-size: cover;
        }
      }
      .P_buying_list {
        width: 100%;
        overflow: hidden;
        margin-top: 50/@rem;
        .list_ul {
          width: 125%;
          height: 245/@rem;
          display: flex;
          text-align: center;
          padding-right: 40/@rem;
          li {
            flex: 1;
            float: left;
            position: relative;
            a {
              display: inline-block;
              width: 160/@rem;
              height: 160/@rem;
              display: inline-block;
              font-size: 28/@rem;
              font-weight: 600;
              color: #706D73;
              img {
                display: inline-block;
                width: 100%;
              }
            }
            span:nth-of-type(1) {
              font-style: normal;
              color: red;
              font-size: 28/@rem;
              font-weight: 600;
              position: absolute;
              bottom: 40/@rem;
              left: 50/@rem;
            }
            span:nth-of-type(2) {
              color: #A7A7A5;
              font-style: normal;
              font-size: 14/@rem;
              position: absolute;
              bottom: 0/@rem;
              left: 50/@rem;
            }
          }
        }
      }
    }
    .index_discount {
      width: 100%;
      height: 380/@rem;
      margin-top: 30/@rem;
      background: #FFFFF3;
      .discount_img {
        width: 100%;
        img {
          width: 100%;
        }
      }
    }
    .index_recommend {
      width: 100%;
      height: 500/@rem;
      margin-top: 20/@rem;
      position: relative;
      .recommend_imgR {
        width: 380/@rem;
        img {
          width: 100%;
          margin: 2/@rem;
        }
      }
      .hr {
        height: 480/@rem;
        width: 1px;
        background: #DEDEDE;
        position: absolute;
        top: 30/@rem;
        left: 380/@rem;
      }
      .recommend_imgL {
        width: 367/@rem;
        .hr {
          height: 1px;
          background: #DEDEDE;
          width: 350/@rem;
          position: absolute;
          top: 50%;
          right: 10/@rem;
        }
        .img2 {
          width: 100%;
          height: 250/@rem;
          position: relative;
          img {
            width: 100%;
            height: 100%;
            position: absolute;
            top: 2/@rem;
            left: 0;
          }
        }
        .img1 {
          width: 100%;
          height: 251/@rem;
          position: relative;
          img {
            width: 100%;
            height: 100%;
            position: absolute;
            top: 0;
            left: 0;
          }
        }
      }
    }
    /*特卖组件*/
    .index_sale {
      width: 100%;
      /*height: 400/@rem;*/
      position: relative;
      background: #ffffff;
      .sale_top {
        width: 100%;
        margin-top: 18/@rem;
        height: 176/@rem;
        .img_left {
          margin: 28/@rem 0 0 0;;
          position: absolute;
          top: 0;
          left: 20/@rem;
          width: 330/@rem;
          height: 110/@rem;
          background-image: url("./recomment.jpg");
          background-repeat: no-repeat;
          background-size: cover;
        }
        text-align: center;
        line-height: 90/@rem;
        .img_right {
          position: absolute;
          top: 34/@rem;
          right: 32/@rem;
          width: 100/@rem;
          height: 50/@rem;
          background-image: url("./more1.png");
          background-repeat: no-repeat;
          background-size: cover;
        }
      }
      .sale_list {
        width: 100%;
        margin-top: 20/@rem;
        img {
          width: 100%;
        }
      }
    }
    /*体验馆组件*/
    .index_experience_hall {
      width: 100%;
      /*height: 400/@rem;*/
      position: relative;
      background: #ffffff;
      .experience_hall_top {
        width: 100%;
        margin-top: 18/@rem;
        height: 176/@rem;
        .img_left {
          margin: 28/@rem 0 0 0;;
          position: absolute;
          top: 0;
          left: 20/@rem;
          width: 330/@rem;
          height: 110/@rem;
          background-image: url("./tiyan.jpg");
          background-repeat: no-repeat;
          background-size: cover;
        }
        text-align: center;
        line-height: 90/@rem;
        .img_right {
          position: absolute;
          top: 34/@rem;
          right: 32/@rem;
          width: 100/@rem;
          height: 50/@rem;
          background-image: url("./more1.png");
          background-repeat: no-repeat;
          background-size: cover;
        }
      }
    }
    /*萌宠说*/
    .adorable_pet {
      width: 100%;
      /*height: 400/@rem;*/
      position: relative;
      background: #ffffff;
      .play {
        position: absolute;
        left: 0;
        right: 0;
        top: 350/@rem;
        bottom: 0;
        margin: 0 auto;
        width: 60/@rem;
        height: 60/@rem;
        background-image: url("./play2.png");
        background-repeat: no-repeat;
        background-size: cover;
      }
      .adorable_pet_top {
        width: 100%;
        margin-top: 18/@rem;
        height: 156/@rem;
        .img_left {
          margin: 28/@rem 0 0 0;;
          position: absolute;
          top: 0;
          left: 20/@rem;
          width: 330/@rem;
          height: 110/@rem;
          background-image: url("./cats.jpg");
          background-repeat: no-repeat;
          background-size: cover;
        }
        text-align: center;
        line-height: 90/@rem;
        .img_right {
          position: absolute;
          top: 34/@rem;
          right: 32/@rem;
          width: 100/@rem;
          height: 50/@rem;
          background-image: url("./more1.png");
          background-repeat: no-repeat;
          background-size: cover;
        }
      }
      .sale_list {
        width: 100%;
        margin-top: 20/@rem;
        img {
          width: 100%;
        }
      }
    }
    .adorable_pet {
      height: 714/@rem;
      position: relative;
      .adorable_pet_text {
        text-align: center;
        font-size: 20/@rem;
      }
      .adorable_pet_look {
        text-align: center;
        font-size: 20/@rem;
        position: relative;
        color: #A7A7A5;
        i {
          line-height: 60/@rem;
          font-style: normal;
          color: #A7A7A5;
          margin-left: 20/@rem;
        }
        i:nth-of-type(2) {
          height: 20/@rem;
          width: 1px;
          background: #A7A7A5;
          position: absolute;
          top: 20/@rem;
          left: 50%;
        }
        i:nth-of-type(3) {
          margin-left: 80/@rem;
        }
      }
    }
    /*小剧场*/
    .Theatre {
      width: 100%;
      /*height: 400/@rem;*/
      position: relative;
      background: #ffffff;
      .play {
        position: absolute;
        left: 0;
        right: 0;
        top: 350/@rem;
        bottom: 0;
        margin: 0 auto;
        width: 60/@rem;
        height: 60/@rem;
        background-image: url("./play2.png");
        background-repeat: no-repeat;
        background-size: cover;
      }
      .Theatre_top {
        width: 100%;
        margin-top: 18/@rem;
        height: 156/@rem;
        .img_left {
          margin: 28/@rem 0 0 0;;
          position: absolute;
          top: 0;
          left: 20/@rem;
          width: 330/@rem;
          height: 110/@rem;
          background-image: url("./Theatre.jpg");
          background-repeat: no-repeat;
          background-size: cover;
        }
        text-align: center;
        line-height: 90/@rem;
        .img_right {
          position: absolute;
          top: 34/@rem;
          right: 32/@rem;
          width: 100/@rem;
          height: 50/@rem;
          background-image: url("./more1.png");
          background-repeat: no-repeat;
          background-size: cover;
        }
      }
      .sale_list {
        width: 100%;
        margin-top: 20/@rem;
        img {
          width: 100%;
        }
      }
    }
    .while {
      height: 95/@rem;
    }
  }
</style>
