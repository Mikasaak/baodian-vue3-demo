<script setup>
import "../styles/custom-element-plus.scss"
import {reactive,onMounted} from 'vue'
import {ref} from 'vue'

const formInline = reactive({
  search: '',
})
const getFatherElementWidth = (el) => {
  let width = el.offsetWidth
  let style = window.getComputedStyle(el)
  width += parseInt(style.marginLeft) + parseInt(style.marginRight)
  return width
}
const onSubmit = () => {
  console.log('submit!')
}
const menuInfo = reactive([
  {
    title: '首页',
    index: '1',
  },
  {
    title: '模拟考试',
    index: '2',
    children: [
      {
        title: '科目一',
        index: '2-1',
      },
      {
        title: '科目二',
        index: '2-2',
      },
      {
        title: '科目三',
        index: '2-3',
      },
      {
        title: '科目四',
        index: '2-4',
      },
    ],

  },
  {
    title: '找驾校',
    index: '3',
    children: [
      {
        title: '找驾校',
        index: '3-1',
      },
      {
        title: '找教练',
        index: '3-2',
      },
      {
        title: '找陪练',
        index: '3-3',
      }
    ]
  },
  {
    title: '考驾圈',
    index: '4',
  },
  {
    title: '交通标志',
    index: '5',
  },
  {
    title: '软件下载',
    index: '6',
  },
  {
    title: '驾考宝典企业版',
    index: '7',
  },
  {
    title: '智慧驾校',
    index: '8',
  },
  {
    title: "买新车",
    index: '9',
    children: [
      {
        title: '买车网',
        index: '9-1',
      },
      {
        title: '平行之家',
        index: '9-2',
      }
    ]
  },
  {
    title: "二手车",
    index: '10'
  },

])
const collapseTransition = ref(false)

const activeIndex = ref('1')
const handleSelect = (key, keyPath) => {
  console.log(key, keyPath)
}

//处理子菜单的宽度
const subMenuHeights = ref([])
onMounted(()=>{
  const subMenu = document.querySelectorAll('.el-sub-menu')
  console.log(subMenu)
  subMenu.forEach((item)=>{
    let width = item.offsetWidth
    let index = item.dataset.index
    menuInfo[index-1].width = width
  })
})


</script>

<template>
  <nav class="nav clearfix">
    <div class="navigation-top clearfix">
      <div class="logo">
        <a href="#">
          <img src="../assets/images/logo.png" alt="">
        </a>
      </div>
      <div class="search">
        <el-form :inline="true" :model="formInline" class="demo-form-inline">
          <el-form-item>
            <el-input v-model="formInline.search" placeholder="请输入关键词" clearable/>
          </el-form-item>
          <el-form-item>
            <el-button type="primary" @click="onSubmit">搜索</el-button>
          </el-form-item>
        </el-form>
      </div>
    </div>
    <div class="navigation-content">
      <div class="menu">
        <el-menu
            :default-active="activeIndex"
            class="el-menu-demo"
            mode="horizontal"
            @select="handleSelect"
            text-color="#fff"
            active-text-color="#fff"
            background-color="#258fc7"
        >
          <el-menu-item v-for="(item,index) in menuInfo" :key="item.index" :index="item.index"
                        :class="{'no-padding':item.children ,
                        'menu-item':true}">
            {{ item?.children ? '' : item.title }}
            <el-sub-menu v-if="item.children" :index="item.index" :data-index="index+1">
              <template #title>{{ item.title }}</template>
              <el-menu-item  v-for="child in item.children" :key="child.index" :index="child.index" class="sub-item"
              :style="{
                backgroundColor: '#fff',
                width: `${menuInfo[index].width}px`,
                display: 'flex',
                justifyContent: 'center',
              }">
                {{ child.title }}
              </el-menu-item>
            </el-sub-menu>
          </el-menu-item>
        </el-menu>
      </div>
    </div>
  </nav>
</template>

<style scoped lang="scss">
nav {
  width: 100%;
  height: 148px;
  overflow: hidden;
  //background-color: skyblue;
  .navigation-top {
    width: 1200px;
    height: 42px;
    margin: 28px auto;
  }

  .logo {
    float: left;

    a {
      display: block;
    }
  }

  .search {
    float: right;
  }

  .navigation-content {
    background-color: #37b5f8;
    .menu {
      width: 1200px;
      height: 50px;
      margin: 0 auto;

      .el-menu-demo {
        height: 100%;
      }
      .menu-item{//设置菜单项的样式
        font-family: "Microsoft YaHei", serif;
        line-height: 50px;
        text-align: center;
        font-size: 16px;
      }
      :deep(.el-sub-menu__title) {
        font-family: "Microsoft YaHei", serif;
        line-height: 50px;
        text-align: center;
        font-size: 16px;
        padding-right: unset;
      }
      :deep(.el-menu--horizontal.el-menu){
        border-bottom: none!important;//去掉菜单下方的一条线
      }

      :deep(.el-menu--horizontal>.el-menu-item) {
        border-bottom: none !important;//原来的选中的下方有一条线，去掉
        //height: 100%!important;
      }

      :deep(.el-sub-menu__title) {
        height: 100% !important;//
        &:after {
          box-sizing: border-box;
          display: inline-block;
          vertical-align: middle;
          width: 10px;
          height: 10px;
          margin-left: 6px;
          margin-top: 5px;
          border: 5px solid transparent;
          border-top: 5px solid #fff;
          content: ' ';
        }
      }
      :deep(.el-icon.el-sub-menu__icon-arrow) {
         display: none!important;
      }
      :deep(.el-sub-menu) {
        height: 100% !important;
        min-width: 108px !important;//设置子菜单最小的宽度
      }

      :deep(.el-menu-item) {
        min-width: 108px !important;
      }

      .no-padding {
        padding: 0 !important;//去除包括submenu的menu-item的padding
      }

      .el-menu-demo {
        width: 100%;
        background-color: #37b5f8;
      }
    }
  }
}

:deep(.el-form-item) {
  margin-right: 0;
}


:deep(el-menu-item) {

}
//子菜单选项的样式
.sub-item {
  color: #000!important;
  font-family: "Microsoft YaHei", serif;
  line-height: 40px;
  text-align: center;
  font-size: 14px;
  &:hover {
    color: skyblue !important;
  }
}



</style>
