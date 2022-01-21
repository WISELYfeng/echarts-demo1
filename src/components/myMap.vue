<template>
  <div id="main" style="width: 1200px; height: 800px"></div>
  <button @click="initMap">生成地图</button>
</template>
<script>
import * as echarts from 'echarts'
import geo from '@/map/london.json'
export default {
  setup() {
    const initMap = () => {
      console.log(111111111)
      // 基于准备好的dom，初始化echarts实例
      const myChart = echarts.init(document.getElementById('main'))
      console.log(myChart)
      // 绘制图表
      echarts.registerMap('UnitedKindom', geo)
      myChart.setOption({
        geo: [
          {
            map: 'UnitedKindom',
            aspectScale: 0.75,
            zoom: 1,
          },
        ],
      })
      // myChart.setOption({
      //   title: {
      //     text: 'ECharts 入门示例',
      //   },
      //   tooltip: {},
      //   xAxis: {
      //     data: ['衬衫', '羊毛衫', '雪纺衫', '裤子', '高跟鞋', '袜子'],
      //   },
      //   yAxis: {},
      //   series: [
      //     {
      //       name: '销量',
      //       type: 'bar',
      //       data: [5, 20, 36, 10, 10, 20],
      //     },
      //   ],
      // })
    }
    return {
      initMap,
    }
  },
}
</script>
<style scoped></style>
