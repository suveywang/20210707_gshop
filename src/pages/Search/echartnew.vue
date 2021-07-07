<template>
  <div class="line" style="font-size: 20px">
    <div class="main" ref="main"  style="font-size: 20px">
    </div>
  </div>
</template>
<script>
  let echarts = require('echarts/lib/echarts');//引入echarts
  require('echarts/lib/chart/bar'); //引入柱状图
  // 引入提示框和标题组件
  require('echarts/lib/component/tooltip');
  require('echarts/lib/component/title');

  export default{
    data(){
      return{
        myChart:{}
      }
    },
    mounted(){
      this.initEcharts();
    },
    methods:{
      initEcharts(){
        let THIS=this;
        let mainDiv = THIS.$refs.main; //找到绘制的区域,强烈推荐使用refs
        var myChart = echarts.init(mainDiv); //初始化
        myChart.setOption({ //官网例子
          title: {
            text: '区域分布数据'
          },
          tooltip: {},
          xAxis: {
            data: ['福田区', '罗湖区', '龙岗区', '盐田区', '南山区', '宝安区']
          },
          yAxis: {},
          series: [{
            name: '销量',
            type: 'bar',
            data: [5, 20, 36, 10, 10,20]
          }]
        });
      }
    }
  }
</script>
<style lang='stylus' scoped>
  .line
    height 100%
    .main
      width:400px; //宽高也不可少
      height:180px;


</style>
