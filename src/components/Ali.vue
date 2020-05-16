<template>
  <div>
    <div class="main">
      <div class="search">
        <a href="#">
          <div class="left">
            <img src="../assets/image/main-search.png" alt />
            <span>阿里集市</span>
            <input type="text" />
          </div>
        </a>
        <div class="right">
          <a href="#">
            <img src="../assets/image/btn.png" alt />
          </a>
        </div>
      </div>
      <div class="nav">
        <ul>
          <li
            class="nav-li"
            v-for="(item, i) in navdata"
            :key="i"
            @click="navClick(i)"
            :class="navActive == i ? 'navActive' : '' "
          >
            <a href="#">{{item.data}}</a>
          </li>
        </ul>
      </div>
      <div class="swiper">
        <mt-swipe :auto="4000">
          <mt-swipe-item>
            <a href="#"><img src="../assets/image/banner1.png" alt /></a>
          </mt-swipe-item>
          <mt-swipe-item>
            <a href="#"><img src="../assets/image/banner2.png" alt /></a>
          </mt-swipe-item>
        </mt-swipe>
      </div>
      <div class="content">
        <ul class="content-butn">
          <li class="butn-box" v-for="(item, index) in butndata" :key="index">
            <a href="#" >
              <img :src="item.img" class="butn-icon" />
            <span class="butn-text">{{item.data}}</span>
            </a>
          </li>
        </ul>
      </div>
      <div class="footer">
        <a href="#" v-for="(item, i) in footerdata" :key="i" @click="ftClick(i)" :class="ftActive == i? 'ftActive' : ''">
          <img :src="item.img"  v-if="ftActive !==i" />
          <img :src="item.active" v-if="ftActive ==i"/>
          <p>{{item.data}}</p>
        </a>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      navdata: {
        1: {
          data: '时尚'
        },
        2: {
          data: '美妆'
        },
        3: {
          data: '食品'
        },
        4: {
          data: '居家'
        },
        5: {
          data: '母婴'
        },
        6: {
          data: '全球'
        },
        7: {
          data: '粮食'
        },
        8: {
          data: '养生'
        }
      },
      butndata: {
        1: {
          data: '食品美鲜',
          img: require('../assets/image/butn1.png')
        },
        2: {
          data: '美妆护肤',
          img: require('../assets/image/butn2.png')
        },
        3: {
          data: '居家生活',
          img: require('../assets/image/butn3.png')
        },
        4: {
          data: '母婴产品',
          img: require('../assets/image/butn4.png')
        },
        5: {
          data: '全球购',
          img: require('../assets/image/butn5.png')
        },
        6: {
          data: '粮油厨房',
          img: require('../assets/image/butn6.png')
        },
        7: {
          data: '在线客服',
          img: require('../assets/image/butn7.png')
        },
        8: {
          data: '直播',
          img: require('../assets/image/butn8.png')
        },
        9: {
          data: '健康养生',
          img: require('../assets/image/butn9.png')
        },
        10: {
          data: '时尚服饰',
          img: require('../assets/image/butn10.png')
        }
      },
      footerdata: {
        1: {
          data: '首页',
          img: require('../assets/image/footer-1.png'),
          active: require('../assets/image/footer1.png')
        },
        2: {
          data: '分类',
          img: require('../assets/image/footer-2.png'),
          active: require('../assets/image/footer2.png')
        },
        3: {
          data: '发现',
          img: require('../assets/image/footer-3.png'),
          active: require('../assets/image/footer-3.png')
        },
        4: {
          data: '购物车',
          img: require('../assets/image/footer-4.png'),
          active: require('../assets/image/footer4.png')
        },
        5: {
          data: '我的',
          img: require('../assets/image/footer-5.png'),
          active: require('../assets/image/footer5.png')
        }
      },
      navActive: 1,
      ftActive: '1'
    }
  },
  created() {
  },
  methods: {
    navClick(i) {
      this.navActive = i
    },
    ftClick(i) {
      this.ftActive = i
    }
  }
}
</script>
<style lang="less" scoped>
.main {
  background: #fff;
  width: 100%;
  height: auto;
  margin-bottom: 80px;
  border-left: #9e101c;
  border-right: #9e101c;
  .search {
    margin-top: 15px;
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding-bottom: 22px;
    .left {
      position: relative;
      margin-left: 11px;
      padding: 6px 22px 6px 11px;
      border-radius: 5px;
      display: flex;
      align-items: center;
      background-color: #f5f5f5;
      img {
        width: 23px;
        height: 23px;
      }
      span {
        width: 30%;
        display: inline-block;
        color: #d41b23;
        font-weight: bolder;
        font-size: 18px;
        padding: 0 5px 0 10px;
      }
      input {
        border: none;
        width: 200px;
        background: #f5f5f5;
      }
    }
    .right {
      width: 35px;
      height: 35px;
      padding-top: 5px;
      position: absolute;
      right: 10px;
      a {
        display: block;
        img{
        width: 100%;
        height: 100%;
        }
      }
    }
  }
  .nav {
    margin-top: 5px;
    ul {
      white-space: nowrap;
      overflow: scroll;
      &::-webkit-scrollbar {
        display: none;
      }
      .nav-li {
        width: 33px;
        margin-left: 15px;
        margin-right: 35px;
        text-align: center;
        height: 33px;
        line-height: 33px;
        font-size: 16px;
        display: inline-block;
        a {
          font-size: 16 px;
          color: #000;
        }
      }
    }
  }
  .swiper {
    height: 187px;
    position: relative;
    bottom: -10px;
    .mint-swipe-item {
      img {
        width: 100%;
        height: 100%;
      }
    }
  }
  .content {
    margin-top: 35px;
    .content-butn {
      width: 100%;
      display: -ms-flexbox;
      display: flex;
      -ms-flex-wrap: wrap;
      flex-wrap: wrap;
      -ms-flex-pack: justify;
      justify-content: space-between;
      .butn-box {
        width: 20%;
        text-align: center;
        margin-bottom: 17px;
        a{
          display: block;
          .butn-icon {
            width: 63.4%;
          }
          .butn-text {
            font-size: 14px;
            color: #000;
            display: block;
          }
        }
      }
    }
  }
}
.footer {
  position: fixed;
  left: 0;
  bottom: 0;
  width: 100%;
  height: 78px;
  -ms-flex: 1;
  flex: 1;
  background: #fff;
  -ms-flex-pack: distribute;
  justify-content: space-around;
  z-index: 100;
  border-top: 1px solid #d6d6d6;
  display: flex;
  align-items: center;
  font-size: 12px;
  a {
    flex-direction: column;
    display: flex;
    align-items: center;
    color: #a2a2a2;
    img {
      width: 34px;
      height: 34px;
    }
    p {
      display: block;
    }
  }
}
.navActive {
  color: rgb(158, 16, 28);
  border-bottom: 3px solid rgb(158, 16, 28);
}
.ftActive{
  color: red !important;
}
</style>
