<template>
    <div class="headpieceDiagram">
        <p class="headpieceDiagramP">每日发送量对比</p>
        <!--<div class="headpieceDiagramDiv"></div>-->
        <div id="myChart" :style="{ width: '1240px', height: '220px' }"></div>
    </div>
</template>

<script>
export default {
    name: 'headpieceDiagram',
    data () {
        return {

        }
    },
    mounted () {
        this.drawLine()
    },
    methods: {
        drawLine () {
            let myChart = this.$echarts.init(document.getElementById('myChart'))
            myChart.setOption({
                tooltip: {
                    trigger: 'axis',
                    show: true,
                    triggerOn: 'none'
                },
                legend: {
                    show: false
                },
                grid: {
                    left: '30',
                    right: '0%',
                    bottom: '0%',
                    containLabel: true
                },
                xAxis: {
                    type: 'category',
                    show: true,
                    boundaryGap: true,
                    splitLine: {
                        show: true,
                        lineStyle:{
                            color: ['#61bcff'],
                            width: 1,
                            type: 'solid'
                        }
                    },
                    data: ['1','2','3','4','5','6','7','8','9','10']
                },
                yAxis: {
                    type: 'value',
                    //网格样式
                    show: true,
                    boundaryGap: true,
                    axisLabel: {
                        color: '#fff'
                    },
                    splitLine: {
                        show: true,
                        lineStyle:{
                            color: ['#61bcff'],
                            width: 1,
                            type: 'solid'
                        }
                    }
                },
                series: [
                    {
                        name:'3',
                        type:'line',
                        smooth:true,
                        color: '#EE9D29',
                        stack: '1',
                        data:[2000, 100, 200, 300, 90, 230, 210,144,544,666]
                    },
                    {
                        name:'2',
                        type:'line',
                        smooth:true,
                        color: '#2CEAA0',
                        stack: '2',
                        data:[100, 200, 191, 234, 290, 330, 310, 244, 5330, 100]
                    },
                    {
                        name:'1',
                        type:'line',
                        smooth:true,
                        color: '#61bcff',
                        stack: '3',
                        data:[300, 300, 201, 154, 190, 330, 410,2211, 242, 100],
                    }
                ]
            })
            myChart.dispatchAction({
                type: 'showTip',
                seriesIndex: 2,
                dataIndex: 0
            });
        }
    }
}
</script>

<style scoped lang="stylus" rel="stylesheet/stylus">
    @import "../../../common/stylus/variable.styl"
.headpieceDiagram
    width 1240px
    margin 0 10px
    position relative
    overflow hidden
    .headpieceDiagramDiv
      position absolute
      top 0
      height 20px
      z-index 11111
      background red
      width 100px
    .headpieceDiagramP
       position absolute
       top 0
       left 0
       height 30px
       line-height 30px
       text-align center
       font-size 16px
       color $color-white
       width 120px
</style>