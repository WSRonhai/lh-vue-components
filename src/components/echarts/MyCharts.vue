<template>
  <div
    ref="echarts"
    :style="{ width: eWidth + 'px', height: eHight + 'px' }"
  ></div>
</template>

<script>
import * as echarts from "echarts";
export default {
  props: ["eWidth", "eHight", "option"],
  data() {
    return {};
  },
  mounted() {
    this.$nextTick(() => {
      this.initData();
    });
  },
  methods: {
    initData() {
      var myChart = echarts.init(this.$refs.echarts);
      // 使用刚指定的配置项和数据显示图表。
      this.option && myChart.setOption(this.option);
    },
  },
};
</script>

<style lang="scss" scoped></style>
