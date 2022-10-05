<template>
  <div class="avatar-list">
    <div class="tabbar" ref="bigBox">
      <div
        class="left-icon"
        v-if="avatarList.length > 5"
        @click="handleLeft"
      ></div>
      <div
        class="tabbar-item"
        v-for="(item, index) in avatarList"
        :key="item.id"
        ref="BoxItem"
        :style="moveItem"
      >
        <img :src="item.url" alt="" class="img" />
        <div class="name">{{ item.name }}</div>
      </div>
      <div
        class="right-icon"
        v-if="avatarList.length > 5"
        @click="handleRight"
      ></div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Home",
  props: ["avatarList"],
  data() {
    return {
      itemWidth: 0,
      BoxWidth: 0,
      moveWidht: 0,
      currentIndex: 0,
    };
  },
  computed: {
    moveItem() {
      return {
        transform: `translateX(${this.moveWidht}px)`,
      };
    },
  },
  methods: {
    getTabbarWidht() {
      let itemObj = this.$refs.bigBox.getBoundingClientRect();
      this.BoxWidth = itemObj.width;
    },
    getTabbarItemWidth() {
      let itemObj = this.$refs.BoxItem[0].getBoundingClientRect();
      this.itemWidth = itemObj.width;
      console.log(this.itemWidth, this.BoxWidth);
    },
    handleLeft() {
      if (this.currentIndex > 0) {
        this.currentIndex--;
        if (this.currentIndex == 1) {
          this.moveWidht =
            (this.itemWidth * this.currentIndex + 10 * this.currentIndex + 10) *
            -1;
        } else {
          this.moveWidht =
            (this.itemWidth * this.currentIndex + 10 * this.currentIndex) * -1;
        }
        console.log("left", this.currentIndex, this.moveItem, this.moveWidht);
      }
    },
    handleRight() {
      if (this.currentIndex < this.avatarList.length - 4) {
        this.currentIndex++;
        if (this.currentIndex == this.avatarList.length - 4) {
          this.moveWidht =
            (this.itemWidth * this.currentIndex + 10 * this.currentIndex) * -1;
        } else {
          this.moveWidht =
            (this.itemWidth * this.currentIndex + 10 * this.currentIndex + 10) *
            -1;
        }
        console.log("right", this.currentIndex, this.moveItem, this.moveWidht);
      }
    },
  },
  mounted() {
    this.$nextTick(() => {
      this.getTabbarWidht();
      this.getTabbarItemWidth();
    });
  },
};
</script>

<style scoped lang="scss">
.avatar-list {
  margin: 0 auto;
  width: 100%;
  padding: 10px;
  box-sizing: border-box;
  min-height: 150px;

  .tabbar {
    width: 320px;
    display: flex;
    justify-content: space-between;
    align-items: center;
    position: relative;
    border: 1px solid #ccc;
    box-sizing: border-box;
    overflow: hidden;
    padding-top: 10px;
    padding-bottom: 10px;

    .tabbar-item {
      width: 9999px;
      margin-right: 10px;
      box-sizing: border-box;
      text-align: center;
      transition: 0.5s ease;

      .name {
        width: 70px;
        display: inline-block;
      }

      .img {
        width: 60px;
        height: 60px;
        border-radius: 10px;
      }
    }

    .left-icon {
      width: 20px;
      z-index: 999;
      height: 20px;
      background-color: salmon;
      position: absolute;
      border-radius: 10px;
      top: 40px;
      left: 5px;
      opacity: 0.8;
      cursor: pointer;
    }

    .right-icon {
      width: 20px;
      height: 20px;
      z-index: 999;
      background-color: salmon;
      position: absolute;
      border-radius: 10px;
      top: 40px;
      right: 5px;
      opacity: 0.8;
      cursor: pointer;
    }
  }
}
</style>
