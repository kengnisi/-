<template>
  <div>
    <div class="header">搜索用户数<span><svg t="1649750560419" class="icon" viewBox="0 0 1024 1024" version="1.1" xmlns="http://www.w3.org/2000/svg" p-id="4957" width="16" height="16"><path d="M512 958.016C266.08 958.016 65.984 757.952 65.984 512 65.984 266.08 266.08 65.984 512 65.984c245.952 0 446.016 200.064 446.016 446.016C958.016 757.952 757.952 958.016 512 958.016zM512 129.984C301.344 129.984 129.984 301.344 129.984 512c0 210.624 171.36 382.016 382.016 382.016 210.624 0 382.016-171.36 382.016-382.016C894.016 301.344 722.624 129.984 512 129.984z" p-id="4958" fill="#bfbfbf"></path><path d="M512 304m-48 0a1.5 1.5 0 1 0 96 0 1.5 1.5 0 1 0-96 0Z" p-id="4959" fill="#bfbfbf"></path><path d="M512 768c-17.664 0-32-14.304-32-32l0-288c0-17.664 14.336-32 32-32s32 14.336 32 32l0 288C544 753.696 529.664 768 512 768z" p-id="4960" fill="#bfbfbf"></path></svg></span></div>
    <div class="main">
      12321
      <span>17.1
        <svg t="1649487813190" class="icon" viewBox="0 0 1025 1024" version="1.1" xmlns="http://www.w3.org/2000/svg" p-id="38957" width="16" height="16"><path d="M131.339914 423.017198c-9.52111 9.670597-9.400291 25.229558 0.270306 34.750668 9.670597 9.522134 25.229558 9.401315 34.750668-0.269282l320.722863-325.740925 0 798.397108c0 13.5716 11.001648 24.573248 24.573248 24.573248 13.5716 0 24.573248-11.001648 24.573248-24.573248L536.230246 135.522485l315.80719 320.551874c9.523157 9.667525 25.084167 9.783224 34.750668 0.259043 9.667525-9.524181 9.784248-25.083143 0.259043-34.750668L552.305246 81.813557c-11.058985-11.331339-25.865391-17.688643-41.702849-17.905707-0.277473-0.004096-0.554946-0.005119-0.832419-0.005119-15.559985 0-30.237381 5.957989-41.412066 16.831651-0.124914 0.121842-0.249828 0.245732-0.372694 0.370646L131.339914 423.017198z" p-id="38958" fill="#1afa29"></path></svg>
        <svg t="1649487868981" class="icon" viewBox="0 0 1025 1024" version="1.1" xmlns="http://www.w3.org/2000/svg" p-id="39854" width="16" height="16"><path d="M467.985218 937.525717c0.122866 0.124914 0.24778 0.248804 0.372694 0.370646 11.174684 10.873662 25.852081 16.831651 41.412066 16.831651 0.277473 0 0.554946-0.001024 0.832419-0.005119 15.837458-0.217064 30.643864-6.574368 41.702849-17.905707l334.741901-339.769178c9.525205-9.667525 9.408482-25.226487-0.259043-34.750668-9.666501-9.524181-25.227511-9.408482-34.750668 0.259043l-315.80719 320.551874L536.230246 88.475979c0-13.5716-11.001648-24.573248-24.573248-24.573248-13.5716 0-24.573248 11.001648-24.573248 24.573248l0 798.397108L166.360888 561.132161c-9.52111-9.670597-25.080071-9.791415-34.750668-0.269282-9.670597 9.52111-9.791415 25.080071-0.270306 34.750668L467.985218 937.525717z" p-id="39855" fill="#d81e06"></path></svg>
      </span>
    </div>
    <div ref="charts" class="charts"></div>
  </div>
</template>

<script>
import * as echarts from "echarts";
export default {
  name: "lineCharts",

  data() {
    return {};
  },

  mounted() {
    let myChart = echarts.init(this.$refs.charts);
    // 绘制图表
    myChart.setOption({
      xAxis: {
        //隐藏x轴
        show: false,
        type: "category",
      },
      yAxis: {
        //隐藏y轴
        show: false,
      },
      //系列
      series: [
        {
          smooth: true,
          type: "line",
          data: [48, 9,29,10,44,10, 7, 33, 12],
          //拐点的样式的设置
          itemStyle: {
            opacity: 0,
          },
          //线条的样式
          lineStyle: {
            color: "purple",
          },
          //填充颜色设置
          areaStyle: {
            color: {
              type: "linear",
              x: 0,
              y: 0,
              x2: 0,
              y2: 1,
              colorStops: [
                {
                  offset: 0,
                  color: "#333", // 0% 处的颜色
                },
                {
                  offset: 1,
                  color: "#fff", // 100% 处的颜色
                },
              ],
              global: false, // 缺省为 false
            },
          },
        },
      ],
      //布局调试
      grid: {
        left: 0,
        top: 0,
        right: 0,
        bottom: 0,
      },
    });

  },

  methods: {},
};
</script>

<style scoped>
.header{
  display: flex;
  align-items: center;
}
.header>span {
  margin-left: 20px;
}
.main {
  margin-top: 20px;
}
.main>span{
  margin-left: 20px;
}
.main>svg {
  margin-left: 10px;
}
.charts {
  width: 100%;
  height: 50px;
}
</style>
