<template>
  <div class="echart-show">
    <MyCharts
      ref="chlid"
      v-if="ordarOption"
      :eWidth="500"
      :eHight="480"
      :option="ordarOption"
    ></MyCharts>
    <MyCharts
      ref="chlid"
      v-if="gaugeOption"
      :eWidth="500"
      :eHight="480"
      :option="gaugeOption"
    ></MyCharts>
    <div @click="handleChange"></div>
  </div>
</template>

<script>
import MyCharts from "@/components/echarts/MyCharts";
export default {
  components: {
    MyCharts,
  },
  data() {
    return {
      ordarOption: {
        color: ["#E51924", "#2773D5"],
        tooltip: {
          show: true,
        },
        legend: {},
        radar: {
          radius: 150,
          indicator: [
            { name: "AA", max: 100 },
            { name: "BB", max: 100 },
            { name: "CC", max: 100 },
            { name: "DD", max: 100 },
            { name: "EE", max: 100 },
          ],
          axisName: {
            color: "#333",
            fontSize: 14,
            fontWeight: 700,
          },
        },
        series: [
          {
            type: "radar",
            data: [
              {
                value: [33, 53, 55, 8, 90],
                name: "红队",
                lineStyle: {
                  type: "dashed",
                  color: "#E51924",
                  opacity: 0,
                },
                symbolSize: 0,
                areaStyle: {
                  color: "#E51924",
                },
              },
              {
                value: [33, 22, 55, 66, 82],
                name: "蓝队",
                symbolSize: 0,
                lineStyle: {
                  type: "dashed",
                  opacity: 0,
                },
                areaStyle: {
                  color: "#2773D5",
                },
              },
            ],
          },
        ],
      },
      gaugeOption: {
        series: [
          {
            type: "gauge",
            startAngle: 90,
            endAngle: -360,
            color: "#244E8F",
            pointer: {
              show: false,
            },
            progress: {
              show: true,
              overlap: false,
              roundCap: true,
              clip: false,
              itemStyle: {
                borderWidth: 2,
                borderColor: "#244E8F",
              },
            },
            axisLine: {
              lineStyle: {
                width: 16,
              },
            },
            splitLine: {
              show: false,
              distance: 0,
              length: 10,
            },
            axisTick: {
              show: false,
            },
            //刻度
            axisLabel: {
              show: false,
              distance: 50,
            },
            data: [
              {
                value: 80,
                //标题文字
                name: 1 + "/6",
                title: {
                  offsetCenter: ["0%", "-5%"],
                },
                detail: {
                  valueAnimation: true,
                  offsetCenter: ["0%", "15%"],
                },
              },
            ],
            //上面标题
            title: {
              fontSize: 14,
              fontWeight: 700,
            },
            //下面文字
            detail: {
              width: 60,
              height: 20,
              fontSize: 14,
              formatter: "表现力",
            },
          },
        ],
      },
    };
  },
  methods: {
    handleChange() {},
  },
};
</script>

<style lang="scss" scoped>
.echart-show {
  display: flex;
  justify-content: space-between;
}
</style>
