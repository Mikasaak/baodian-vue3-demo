<script setup>

function toTheTop() {
  document.documentElement.scrollTop = 0;
}

</script>

<template>
  <div class="com-home-side-float  ">
    <ul>
      <li class="weixin">
        <div class="box"></div>
      </li>
      <li class="weibo">
        <div class="box"></div>
      </li>
      <li class="yjfk"><span>意见反馈</span>
        <div class="yjfk-menu box">
          <ul>
            <li><span class="title">用户反馈</span>
              <div class="content">400-056-1617（电话）</div>
            </li>
            <li><span class="title">教练反馈</span>
              <div class="content">jiaolian_service@mucang.cn(邮箱)</div>
            </li>
            <li><span class="title">驾校反馈</span>
              <div class="content">jiaxiao_service@mucang.cn(邮箱)</div>
            </li>
            <li><span class="title">学员反馈</span><a class="content">点击提交学员反馈</a></li>
          </ul>
          <div class="jt"></div>
        </div>
      </li>
      <li class="to-top" ref="toTop" @click="toTheTop"><span>返回顶部</span>
        <div class="box"></div>
      </li>
    </ul>
    <button class="btn-close" ref="close"></button>
  </div>
</template>

<style scoped lang="scss">
.com-home-side-float {
  position: fixed;
  right: 0;
  bottom: 102px;
  z-index: 2;
  width: 117px;
  min-height: 258px;
  background: url("../assets/images/side-float-bg.png") center top no-repeat;

  &>ul {
    margin-top: 158px;
    border: 1px solid #e6e6e6;
    border-top: none;
    color: #999;
    font-size: 12px;
    font-family: "Microsoft YaHei", "Hiragino Sans GB", "Hiragino Sans GB W3", "Helvetica Neue", Helvetica, Arial, sans-serif;
    position: relative;

    &>li {
      height: 33px;
      line-height: 33px;
      cursor: pointer;

      .box {
        display: none;
        position: absolute;
      }

      &.weixin {
        .box {
          width: 179px;
          height: 195px;
          top: 25px;
          left: -180px;
          background: url("../assets/images/weixin-box.png") center no-repeat;
        }
      }

      &.weibo {
        .box {
          width: 179px;
          height: 195px;
          top: 62px;
          left: -180px;
          background: url("../assets/images/weibo-box.png") center no-repeat;
        }
      }

      &.yjfk {
        padding-left: 45px;
        background: url("../assets/icons/yjfk-box.png") left 15px center no-repeat #fff;
        background-size: 20px;
        border-bottom: 1px solid #e6e6e6;
        .yjfk-menu {
          display: none;
          position: absolute;
          top: -65px;
          left: -165px;
          width: 170px;
          cursor: default;
          text-indent: 0;
          ul {
            margin-right: 10px;
            padding: 5px 15px;
            border: 1px solid #eee;
            background-color: #fff;
            li {
              text-align: left;
              padding: 8px 0;
              &+li {
                border-top: 1px solid #e9e9e9;
              }
              .title {
                display: block;
                line-height: 1.4;
                font-size: 15px;
                color: #000;
              }
              .content {
                font-size: 12px;
                color: #999;
                line-height: 1.4;
                word-wrap: break-word;
              }
              a.content {
                display: block;
                color: #00f;
              }
            }
          }
          .jt {
            position: absolute;
            height: 0;
            width: 0;
            top: 140px;
            right: 0;
            border: 5px solid transparent;
            border-left: 5px solid #e6e6e6;
          }
        }
      }

      &:hover {
        .box {
          display: block;
        }
      }
    }

    .to-top {
      padding-left: 45px;
      background: url("../assets/icons/to-top-btn.png") left 15px center no-repeat #fff;
      color: #333;
    }


  }

  .btn-close {
    position: absolute;
    right: 0;
    top: 60px;
    width: 20px;
    height: 20px;
    border: none;
  }
}
</style>
