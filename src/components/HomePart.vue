<script setup>
import {ref} from 'vue';

const defaultLink = ref("javascript:;");

//理论考试数据
const theoryTestMenuInfo = ref({
  title: '青岛市2024小车理论考试',
  list: [
    {
      position: 'left',
      title: '科目一交规',
      list: [
        {
          title: '顺序练习',
          desc: '按照顺序练习做题',
        },
        {
          title: '随机练习',
          desc: '按随机顺序做题',
        },
        {
          title: '专项练习',
          desc: '分门别类重点突破',
        },
        {
          title: '难题攻克',
          desc: '准确把握考试难点',
        },
      ],
      btn: '模拟考试',
    }
    ,
    {
      position: 'right',
      title: '科目四安全文明驾驶',
      list: [
        {
          title: '顺序练习',
          desc: '按照顺序练习做题',
        },
        {
          title: '随机练习',
          desc: '按随机顺序做题',
        },
        {
          title: '专项练习',
          desc: '分门别类重点突破',
        },
        {
          title: '难题攻克',
          desc: '准确把握考试难点',
        },
      ],
      btn: '模拟考试',
    }
  ],

})


//驾校推荐数据
const drivingSchoolRecommendTitle = ref('青岛市驾校推荐')
const drivingSchoolRecommendList = ref([
  {
    name: "君达驾校",
    elWidth: "98.00000000000001%",
    feature: [
      "口碑好",
      "规模大",
      "拿本快",
      "包接送"
    ],
    price: "4000",
    btnText: "学车报名",
    imgURL: "https://thirdwx.qlogo.cn/mmopen/vi_32/DYAIOgq83ep5B20GLN9RvUiak0lq1nuBmBGS8cicPlyd3aoEM56ibJJYl3sQjlakKXuQic6cJTMEh31Y4TLS6yrAPw/96",
    content: "杨龙教练绝对的靠谱"
  },
  {
    name: "鲁通达驾校",
    elWidth: "100%",
    feature: [
      "口碑好",
      "规模大",
      "拿本快",
      "包接送"
    ],
    price: "3880",
    btnText: "学车报名",
    imgURL: "https://avatar-user.mucang.cn/user-avatar/default/_WcdV7-1V44.jpg!100x100",
    content: "一流的服务和nice的教练，怕上路的我，在教练指导下，还是克服了害怕。不管怎样，心态很重要，加油💪"
  },
  {
    name: "安信达驾校",
    elWidth: "width: 100%",
    feature: [
      "口碑好",
      "规模大",
      "拿本快",
      "包接送"
    ],
    price: "3800",
    btnText: "学车报名",
    imgURL: "https://avatar-user.mucang.cn/user-avatar/default/8KfCR12oeUM.jpg!100x100",
    content: "教练在教学过程中非常有耐心，一丝不苟的指导我学车。教练教学态度严谨、认真负责"

  },
  {
    name: "鲁科驾校",
    elWidth: "94%",
    feature:
        [
          "口碑好",
          "规模大",
          "拿本快",
          "包接送"
        ],
    price: "4000",
    btnText: "学车报名",
    imgURL: "https://avatar-user.mucang.cn/user-avatar/default/UJWrAa_0nOQ.jpg!100x100",
    content: "好，教练态度，有耐心"
  }

])


// 学车流程数据
const studyStepInfo = ref({
  title: '学车流程',
  desc: '驾考宝典整合学车全流程，驾考宝典为用户提供全方位学车服务',
  list: [
    {
      title: '找驾校',
      desc: '口碑好的驾校',
    },
    {
      title: '科目一',
      desc: '驾驶员理论考试',
    },
    {
      title: '科目二',
      desc: '场地驾驶技能考试科目',
    },
    {
      title: '科目三',
      desc: '机动车驾驶人道路考试',
    },
    {
      title: '科目四',
      desc: '安全文明驾驶常识考试',
    },
    {
      title: '拿本',
      desc: '开心拿本，安全驾驶',
    },
  ]
})


// 宝典荣誉数据
const honorInfo = ref({
  title: '宝典荣誉',
  desc: '强大的驾考功能，优秀的用户体验，我们的愿景是学车无忧，轻松拿本',
})

// APP广告数据
const appAdInfo = ref([
  {
    title: '教练宝典APP',
  },
  {
    title: '驾考宝典APP',
  },
  {
    title: '买车宝典APP',
  },
])

// 驾考宝典APP下载文本数据
const appDownloadInfo = ref([
  {
    position: 'left',
    title: '驾考宝典APP下载',
    desc: '考驾照 用宝典',
  },
  {
    position: 'right',
    title: '驾考宝典微信小程序',
    desc: '无需下载，驾考做题更方便！',
  },
])
</script>

<template>
  <div class="com-home-theory-test-menu com-part-home">
    <div class="part-home-title">
      <hr class="hr">
      <div class="title-text">{{ theoryTestMenuInfo.title }}</div>
    </div>
    <div class="content clearfix">
      <ul class="item left" v-for="(item,index) in theoryTestMenuInfo.list" :key="index" :class="item.position">
        <li class="item-right">
          <a class="link" :href="defaultLink">{{ item.title }}<span class="small"></span></a>
        </li>
        <li class="item-left" v-for="(item,index) in item.list" :key="index" :class="`icon${index+1}`">
          <a :href="defaultLink">{{ item.title }}</a>
          <p>{{ item.desc }}</p>
        </li>
        <li class="item-right btn-bar">
          <a class="btn-link" :href="defaultLink">{{ item.btn }}</a>
        </li>
      </ul>
    </div>
  </div>
  <div class="banner-mid-ad com-part-home">
    <a :href="defaultLink">
      <img src="../assets/images/banner-mid-ad-img.png">
    </a>
  </div>
  <div class="com-home-jiaxiao-tuijian com-part-home">
    <div class="part-home-title">
      <hr class="hr">
      <div class="title-text">{{ drivingSchoolRecommendTitle }}</div>
      <div class="title-text2"></div>
    </div>
    <div class="jiaxiao-tuijian-container">
      <ul class="school-list clearfix">
        <li v-for="(item,index) in drivingSchoolRecommendList" :key="index">
          <div class="item-top clearfix">
            <div class="col1 left">
              <div class="div1"><span class="name">{{ item.name }}</span>
                <div class="star-w-s">
                  <div class="bfb" :style="{'width': item.elWidth}"></div>
                </div>
              </div>
              <div class="div2">
                <span v-for="(itemFeature,index) in item.feature" :key="index">{{ itemFeature }}</span>
              </div>
            </div>
            <div class="col2 left"><p class="price red">￥{{ item.price }}</p></div>
            <div class="col3 right">
              <button class="btn-baoming" data-id="13140">{{ item.btnText }}</button>
            </div>
          </div>
          <div class="item-content">
            <div class="img-w">
              <img :src="item.imgURL">
            </div>
            <p class="content">{{ item.content }}</p></div>
          <div class="tip"></div>
        </li>
      </ul>
      <div class="btn-bar"><a :href="defaultLink">查看更多</a>
      </div>
    </div>
  </div>
  <div class="com-home-study-step com-part-home">
    <div class="part-home-title">
      <hr class="hr">
      <div class="title-text">{{ studyStepInfo.title }}</div>
      <div class="title-text2">{{ studyStepInfo.desc }}</div>
    </div>
    <div class="content">
      <ul class="item clearfix">
        <li class="item-left" v-for="(item,index) in studyStepInfo.list" :key="index" :class="`icon${index+1}`">
          <a :href="defaultLink">
            <span class="title">{{ item.title }}</span>
            <p>{{ item.desc }}</p>
          </a>
        </li>
      </ul>
    </div>
  </div>
  <div class="com-home-my-honor com-part-home">
    <div class="part-home-title">
      <hr class="hr">
      <div class="title-text">{{ honorInfo.title }}</div>
      <div class="title-text2">{{honorInfo.desc}}</div>
    </div>
    <div class="content">
      <img src="../assets/images/honor-bg.png" alt="">
    </div>
  </div>
  <div class="com-home-app-ad">
    <div class="content">
      <div class="item" v-for="(item,index) in appAdInfo" :key="index" :class="`ad${index+1}`"><span>{{item.title}}</span>
        <div></div>
      </div>
    </div>
  </div>
  <div class="com-home-app-down com-part-home">
    <div class="content">
      <ul class="item clearfix">
        <li class="item-left" v-for="(item) in appDownloadInfo" :class="{right:item.position==='right'}">
          <span>{{item.title}}</span>
          <p>{{item.desc}}</p>
        </li>
      </ul>
    </div>
  </div>

</template>

<style lang="scss" scoped>
.left {
  float: left;
}

.right {
  float: right;
}

.red {
  color: #EE4653;
}

button {
  border: 1px solid #e9e9e9;
  font-family: "Microsoft YaHei", "Hiragino Sans GB", "Hiragino Sans GB W3", "Helvetica Neue", Helvetica, Arial, sans-serif;
  background: 0 0;
  border-radius: 0;
}

.com-part-home {
  width: 1200px;
  margin: 60px auto;

  .part-home-title {
    margin-bottom: 40px;
    text-align: center;
    padding-top: 20px;

    .hr {
      height: 1px;
      border: none;
      border-top: 1px dotted #e9e9e9;
    }

    .title-text {
      display: inline-block;
      margin-top: -20px;
      line-height: 41px;
      padding: 0 45px;
      background-color: #fff;
      font-size: 30px;
    }

    .title-text2 {
      font-size: 16px;
      margin: 30px 0;
      color: #666;
    }
  }


}

.com-home-theory-test-menu {
  .content {
    .item {
      border: 1px solid #e9e9e9;
      width: 580px;

      .item-right {
        width: 100%;
        float: right;
        text-align: center;
        height: 110px;
        line-height: 110px;
        padding-top: 0;
        border: none;
        margin: 0;

        .link {
          display: inline-block;
          padding: 0 0 0 38px;
          background: url('../assets/icons/home-part1.png') left center no-repeat;
          font-size: 20px;
          font-family: "Microsoft YaHei", "Hiragino Sans GB", "Hiragino Sans GB W3", "Helvetica Neue", Helvetica, Arial, sans-serif;
          color: rgb(51, 51, 51)
        }
      }

      .item-left {
        float: left;
        width: 250px;
        height: 70px;
        line-height: 20px;
        margin: 0 0 15px 25px;
        padding: 15px 0 15px 85px;
        background-color: #FAFAFA;

        a {
          font-size: 16px;
          font-family: "Microsoft YaHei", "Hiragino Sans GB", "Hiragino Sans GB W3", "Helvetica Neue", Helvetica, Arial, sans-serif;
          color: rgb(51, 51, 51);

          &:hover {
            color: #37B5F8;
          }
        }

        p {
          color: #999;
        }
      }

      .btn-bar {
        height: auto;
        line-height: 70px;

        .btn-link {
          display: block;
          font-size: 18px;
          font-family: "Microsoft YaHei", "Hiragino Sans GB", "Hiragino Sans GB W3", "Helvetica Neue", Helvetica, Arial, sans-serif;
          color: #fff;
          line-height: 44px;
          width: 300px;
          height: 46px;
          border: none;
          margin: 15px auto 30px;
          background: #37B5F8;
          border-radius: 4px;
        }
      }

      .icon1 {
        background-image: url('../assets/icons/home-part-icon1.png');
        background-position: left 50px center;
        background-repeat: no-repeat;
      }

      .icon2 {
        background-image: url('../assets/icons/home-part-icon2.png');
        background-position: left 50px center;
        background-repeat: no-repeat;
      }

      .icon3 {
        background-image: url('../assets/icons/home-part-icon3.png');
        background-position: left 50px center;
        background-repeat: no-repeat;
      }

      .icon4 {
        background-image: url('../assets/icons/home-part-icon4.png');
        background-position: left 50px center;
        background-repeat: no-repeat;
      }
    }
  }
}

.com-home-jiaxiao-tuijian {
  .jiaxiao-tuijian-container {
    margin: 0 auto;

    .school-list {
      margin: -30px 0 0 -30px;
      color: #666;
      font-size: 14px;
      font-family: "Microsoft YaHei", "Hiragino Sans GB", "Hiragino Sans GB W3", "Helvetica Neue", Helvetica, Arial, sans-serif;

      li {
        float: left;
        position: relative;
        width: 585px;
        margin: 30px 0 0 30px;
        padding: 40px 30px;
        border: 1px solid #e9e9e9;

        .item-top {
          .col1 {
            width: 305px;
            line-height: 30px;

            .div1 {
              .name {
                max-width: 180px;
                display: inline-block;
                vertical-align: middle;
                font-size: 22px;
                overflow: hidden;
                white-space: nowrap;
                text-overflow: ellipsis;
              }

              .star-w-s {
                display: inline-block;
                vertical-align: middle;
                margin: -3px 0 0 10px;
                width: 90px;
                height: 20px;
                background: url("../assets/icons/jiaoxiao-tuijian-star.png") left center no-repeat;

                .bfb {
                  height: 100%;
                  background: url(../assets/icons/jiaoxiao-tuijian-star.png) left center no-repeat;
                }
              }
            }

            .div2 {
              margin-top: 10px;
              line-height: 20px;

              span {
                display: inline-block;
                background: url(../assets/icons/jiaoxiao-tuijian-checkmark.png) left center no-repeat;
                padding-left: 20px;

                & + span {
                  margin-left: 10px;
                }
              }
            }
          }

          .col2 {
            width: 130px;
            line-height: 63px;
            border-left: 1px solid #e9e9e9;
            font-size: 30px;
            text-align: center;
          }

          .col3 {
            button {
              width: 80px;
              line-height: 28px;
              margin-top: 17px;
              text-align: center;
              font-size: 14px;
              border-radius: 4px;
            }
          }
        }

        @for $i from 1 through 4 {
          &:nth-child(#{$i}) {
            .img-w {
              background: url('../assets/images/jiaoxiao-tuijian-content-img-bgc#{$i}.png') center center no-repeat;
              background-size: 100% 100%;
            }
          }
        }

        .item-content {
          height: 80px;
          margin-top: 30px;
          padding: 20px;
          background: #FAFAFA;
          color: #999;

          img {
            background: 0 0;
            display: block;
            border: 0;
            max-width: 100%;
          }

          .img-w {
            float: left;
            width: 40px;
            height: 40px;
            border-radius: 50%;
          }

          .content {
            height: 40px;
            line-height: 20px;
            margin-left: 60px;
            display: -webkit-box;
            overflow: hidden;
            text-overflow: ellipsis;
            -webkit-line-clamp: 2;
            line-clamp: 2;
          }
        }

        .tips {
          position: absolute;
          top: 5px;
          right: 10px;
        }
      }
    }

    .btn-bar {
      margin-top: 40px;

      a {
        display: block;
        width: 280px;
        margin: 20px auto 0;
        line-height: 48px;
        border: 1px solid #e9e9e9;
        border-radius: 4px;
        color: #999;
        text-align: center;
        font-size: 16px;
        cursor: pointer;

        &:hover {
          border: 1px solid #37B5F8;
          color: #37B5F8;
        }
      }
    }
  }
}

.banner-mid-ad {
  margin-top: -30px;

  a {
    cursor: pointer;
  }
}

.com-home-study-step {
  .content {
    text-align: center;

    .item {
      margin: 0 -40px;

      li {
        &.item-left {
          float: left;
          width: 16.6%;
          line-height: 1.4;

          a {
            display: block;
            padding: 150px 40px 0;
            color: inherit;
            font-size: inherit;

            .title {
              display: block;
              font-size: 24px;
              font-family: "Microsoft YaHei", "Hiragino Sans GB", "Hiragino Sans GB W3", "Helvetica Neue", Helvetica, Arial, sans-serif;
            }

            p {
              color: #999;
              margin: 10px -20px;
            }
          }
        }

        @for $i from 1 through 6 {
          &.icon#{$i} {
            background: url('../assets/icons/study-step-icon#{$i}.png') center top no-repeat;

            &:hover {
              background: url('../assets/icons/study-step-active-icon#{$i}.png') center top no-repeat;
              color: #37B5F8;
            }
          }

        }
      }
    }
  }
}

.com-home-my-honor {
  .content {
    text-align: center;

    img {
      background: 0 0;
    }
  }


}

.com-home-app-ad {
  background-color: #f5f5f5;

  .content {
    position: relative;
    width: 1200px;
    height: 560px;
    margin: 70px auto 0;
    overflow: hidden;

    .item {
      position: absolute;
      bottom: -40px;
      text-align: center;

      &:hover {
        animation: ad-move 5s ease-out;
        -webkit-animation: ad-move .5s ease-out;
        bottom: 0;

        div {
          display: block;
          animation: none;
          -webkit-animation: none;
        }
      }

      span {
        font-size: 20px;
      }
    }

    @keyframes ad-move {
      0% {
        bottom: -40px;
      }
      100% {
        bottom: 0;
      }
    }


    .ad1 {
      left: 30px;
      width: 300px;
      height: 500px;
      background: url("../assets/images/my-honor-ad1.png") center bottom no-repeat;

      div {
        display: none;
        width: 100%;
        height: 100%;
        margin-top: 37px;
        background: url("../assets/images/my-honor-ad1-div.png") center no-repeat;
      }
    }

    .ad2 {
      left: 400px;
      width: 430px;
      height: 540px;
      background: url("../assets/images/my-honor-ad2.png") center bottom no-repeat;

      div {
        display: none;
        width: 100%;
        height: 100%;
        margin-top: 52px;
        background: url("../assets/images/my-honor-ad2-div.png") center no-repeat;
        background-color: rgba(255, 255, 255, .5);
        background-size: 150px 150px;
      }
    }

    .ad3 {
      left: 905px;
      width: 265px;
      height: 428px;
      background: url("../assets/images/my-honor-ad3.png") center bottom no-repeat;

      div {
        display: none;
        width: 100%;
        height: 100%;
        margin-top: 37px;
        background: url("../assets/images/my-honor-ad3-div.png") center no-repeat;
      }
    }
  }
}

.com-home-app-down {
  .content {
    .item {
      .item-left {
        float: left;
        width: 600px;
        line-height: 1.7;
        margin: 20px 0;
        padding: 40px 80px;
        background: url("../assets/images/app-down-QR-code1.png") right 80px center no-repeat;
        background-size: 140px;
        border-right: 1px solid #e9e9e9;
        &.right {
          float: right;
          background: url("../assets/images/app-down-WeiXin1.png") right 80px center no-repeat;
          background-size: 130px;
          border: none;
        }
        span {
          font-size: 20px;
          font-family: "Microsoft YaHei", "Hiragino Sans GB", "Hiragino Sans GB W3", "Helvetica Neue", Helvetica, Arial, sans-serif;
        }
        p {
          color: #999;
        }
      }
    }
  }
}
</style>
