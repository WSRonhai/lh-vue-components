<template>
  <div class="header">
    <div class="left">
      <AvatarList :avatarList="avatarList"></AvatarList>
    </div>
    <div class="middle">我是一个大标题</div>
    <div class="right">
      <AvatarList :avatarList="avatarList"></AvatarList>
    </div>
  </div>
</template>

<script>
import AvatarList from "@/components/AvatarList";
export default {
  components: {
    AvatarList,
  },
  data() {
    return {
      avatarList: [
        {
          id: 1,
          url: "https://gimg2.baidu.com/image_search/src=http%3A%2F%2Fi.qqkou.com%2Fi%2F0a1749768382x2690711946b26.jpg&refer=http%3A%2F%2Fi.qqkou.com&app=2002&size=f9999,10000&q=a80&n=0&g=0n&fmt=auto?sec=1666926875&t=cbd7937abb7d1ab674ff32e58d071752",
          name: "动画妹",
        },
        {
          id: 2,
          url: "https://gimg2.baidu.com/image_search/src=http%3A%2F%2Fi.qqkou.com%2Fi%2F1a3926195597x528961113b26.jpg&refer=http%3A%2F%2Fi.qqkou.com&app=2002&size=f9999,10000&q=a80&n=0&g=0n&fmt=auto?sec=1666926934&t=b2329f4bd2c7a5686f0ab7899f6adb8c",
          name: "哆啦A梦",
        },
        {
          id: 3,
          url: "https://gimg2.baidu.com/image_search/src=http%3A%2F%2Faaaju.oicp.net%3A93%2Fpicture%2Fbiaoqing%2Fpic%2Fcn%2F20%2F120685.jpeg&refer=http%3A%2F%2Faaaju.oicp.net&app=2002&size=f9999,10000&q=a80&n=0&g=0n&fmt=auto?sec=1666926979&t=b4a5909b1d1a6398f9dfef2dcfa93900",
          name: "海贼王",
        },
        {
          id: 4,
          url: "https://img1.baidu.com/it/u=3314815141,1123698867&fm=253&fmt=auto&app=138&f=JPEG?w=500&h=500",
          name: "猫咪",
        },
        {
          id: 5,
          url: "https://gimg2.baidu.com/image_search/src=http%3A%2F%2Fhbimg.b0.upaiyun.com%2Fef7a5510ff9b25cb79b3898c287240d44f1882691b93-lXYHw2_fw658&refer=http%3A%2F%2Fhbimg.b0.upaiyun.com&app=2002&size=f9999,10000&q=a80&n=0&g=0n&fmt=auto?sec=1666927037&t=12b9f8cfd8b174a39c3466a5adcad589",
          name: "蜡笔",
        },
        {
          id: 6,
          url: "https://gimg2.baidu.com/image_search/src=http%3A%2F%2Fhbimg.b0.upaiyun.com%2Fef7a5510ff9b25cb79b3898c287240d44f1882691b93-lXYHw2_fw658&refer=http%3A%2F%2Fhbimg.b0.upaiyun.com&app=2002&size=f9999,10000&q=a80&n=0&g=0n&fmt=auto?sec=1666927037&t=12b9f8cfd8b174a39c3466a5adcad589",
          name: "蜡笔小",
        },
        {
          id: 7,
          url: "https://gimg2.baidu.com/image_search/src=http%3A%2F%2Fhbimg.b0.upaiyun.com%2Fef7a5510ff9b25cb79b3898c287240d44f1882691b93-lXYHw2_fw658&refer=http%3A%2F%2Fhbimg.b0.upaiyun.com&app=2002&size=f9999,10000&q=a80&n=0&g=0n&fmt=auto?sec=1666927037&t=12b9f8cfd8b174a39c3466a5adcad589",
          name: "蜡笔小新",
        },
      ],
    };
  },
};
</script>

<style lang="scss" scoped>
.header {
  width: 1200px;
  margin: 0 auto;
  box-sizing: border-box;
  display: flex;
  min-height: 150px;
  border: 1px solid skyblue;
  justify-content: space-evenly;
  align-items: center;
  .left {
    width: 400px;
    margin: 0 auto;
  }
  .middle {
    width: 100%;
    text-align: center;
    background-color: #ccc;
    line-height: 150px;
    font-weight: bold;
  }
  .right {
    width: 400px;
  }
}
</style>
