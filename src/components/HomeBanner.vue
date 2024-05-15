<script setup>
import {ref} from 'vue';
// import Swiper core and required modules
import {A11y, Autoplay, Pagination, Scrollbar} from 'swiper/modules';

// Import Swiper Vue.js components
import {Swiper, SwiperSlide} from 'swiper/vue';

// Import Swiper styles
import 'swiper/css';
import 'swiper/css/navigation';
import 'swiper/css/pagination';
import 'swiper/css/scrollbar';


const onSwiper = (swiper) => {
  console.log(swiper);
};
const onSlideChange = () => {
  console.log('slide change');
};
const modules = [Autoplay, Pagination, Scrollbar, A11y];


const menuInfo = ref({
  title: '学车流程',
  list: [
    {
      title: '科目一',
      desc: '2024新题库',
    },
    {
      title: '科目二',
      desc: '精选视频，详解考点',
    },
    {
      title: '科目三',
      desc: '全方位讲解，攻克难点',
    },
    {
      title: '科目四',
      desc: '2024新题库',
    },
  ],

})

/**
 * 返回菜单列表的class
 * @param index
 * @returns {string}
 */
function getMenuListClass(index) {
  return `icon${index}`;
}

function  getMenuIconURL(index) {
  const url = new URL(`../assets/icons/icon${index}.png`, import.meta.url);
  console.log(url);
  return url.href;
}


</script>

<template>
  <div class="home-banner">
    <div class="swiperbox">
      <swiper
          :slidesPerView="1"
          :spaceBetween="30"
          :loop="true"
          :centeredSlides="true"
          :pagination="{
				clickable: true
			}"
          :autoplay="{ delay: 2500, disableOnInteraction: false}"

          :modules="modules"
          class="mySwiper"
      >
        <swiper-slide>
          <a href="#"><img src="../assets/images/home_banner_download.png" alt=""/></a>
        </swiper-slide>
        <swiper-slide>
          <a href="#"><img src="../assets/images/home_banner_new1.jpeg" alt=""/></a>
        </swiper-slide>
        <swiper-slide>
          <a href="#"> <img src="../assets/images/home_banner_jiaolian.jpg" alt=""/></a>
        </swiper-slide>
        <swiper-slide>
          <a href="#"> <img src="../assets/images/home_banner_jiaxiaobang.png" alt=""/></a>
        </swiper-slide>
      </swiper>
    </div>
    <div class="menu">
      <aside class="banner-aside">
        <p class="menu-title">{{ menuInfo.title }}</p>
        <ul class="menu-list">
          <li v-for="(item,index) in menuInfo.list" :key="index"
              :class="getMenuListClass(index+1)"
              :style="{
              backgroundImage: `url(${getMenuIconURL(index+1)})`,
              backgroundRepeat: 'no-repeat',
              backgroundPosition: 'left center'
            }"
          >
            <p class="p1">
              <a href="#" target="_blank">
                {{ item.title }}
              </a>
            </p>
            <p class="p2">{{ item.desc }}</p>
          </li>
        </ul>
      </aside>
    </div>
  </div>
</template>

<style scoped lang="scss">
.swiperbox {
  height: 380px!important;
  :deep(.swiper) {
    height: 380px!important;
  }
  a {
    width: 100%;
    height: 380px;
  }
  img {
    display: block;
    width: auto;
    height: 100%;

  }

  :deep(.el-carousel__item) {
    height: 100%;
  }
}
.menu {
  position: relative;
  width: 1200px;
  margin: 0 auto;
}

.banner-aside {
  position: absolute;
  top: -358px;
  width: 240px;
  height: 336px;
  z-index: 1;
  padding: 0 20px;
  background-color: rgba(255, 255, 255, .9);
  .menu-title {
    width: 240px;
    height: 51px;
    font-family: "Microsoft YaHei",serif;
    font-size: 20px;
    line-height: 50px;
    text-align: center;
    color: #333;
    border-bottom: 1px dotted #ddd;
  }
  .menu-list {
    list-style: none;
    display: flex;
    flex-direction: column;
    height: calc(100% - 51px);
    padding: 0;
    margin: 0;
    li {
      padding: 18px 20px 18px 50px;
      height: 25%;
      .p1 {
        color: #37B5F8;
        font-size: 16px;
        height: 16px;
        a{
          font-size: inherit;
          color: inherit;
        }
      }
      .p2 {
        height: 14px;
        margin-top: 5px;
        color: #666;
      }
    }
  }
}
</style>
