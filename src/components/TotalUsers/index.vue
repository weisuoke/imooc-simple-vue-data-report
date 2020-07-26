<template>
  <common-card
    title="累计用户数"
    value="1,087,503"
  >
    <template>
      <v-chart
        :options="getOptions()"
      />
    </template>
    <template v-slot:footer>
      <div class="total-users-footer">
        <span>日同比</span>
        <span class="emphasis">8.73%</span>
        <div class="increase"></div>
        <span class="month">月同比</span>
        <span class="emphasis">35.91%</span>
        <div class="decrease"></div>
      </div>
    </template>
  </common-card>
</template>

<script>
import commonCardMixin from '../../mixins/commonCardMixin'

export default {
  mixins: [commonCardMixin],
  methods: {
    getOptions () {
      return {
        xAxis: {
          type: 'value',
          show: false
        },
        yAxis: {
          type: 'category',
          show: false
        },
        series: [{
          type: 'bar',
          stack: '总量',
          data: [200],
          barWidth: 10,
          itemStyle: {
            color: '#45c946'
          }
        }, {
          type: 'bar',
          stack: '总量',
          data: [250],
          itemStyle: {
            color: '#eee'
          }
        }, {
          type: 'custom',
          data: [200],
          stack: '总量',
          renderItem: (params, api) => {
            const value = api.value(0)
            const endPoint = api.coord([value, 0])

            return {
              type: 'group',
              position: endPoint,
              children: [{
                type: 'path',
                shape: {
                  d: 'M228.266667 347.733333h569.6c14.933333 0 25.6 4.266667 27.733333 12.8 4.266667 8.533333 0 17.066667-10.666667 27.733334l-281.6 281.6c-4.266667 4.266667-12.8 8.533333-19.2 8.533333-8.533333 0-14.933333-2.133333-19.2-8.533333l-281.6-281.6c-10.666667-10.666667-14.933333-21.333333-10.666666-27.733334 0-8.533333 8.533333-12.8 25.6-12.8z',
                  x: -5,
                  y: -20,
                  width: 10,
                  height: 10,
                  layout: 'cover'
                },
                style: {
                  fill: '#45c946'
                }
              }, {
                type: 'path',
                shape: {
                  d: 'M273.6 593l212.9-212.9c14.1-14.1 36.9-14.1 50.9 0l213 212.9c22.7 22.7 6.6 61.5-25.5 61.5H299.1c-32.1 0-48.1-38.8-25.5-61.5z',
                  x: -5,
                  y: 10,
                  width: 10,
                  height: 10,
                  layout: 'cover'
                },
                style: {
                  fill: '#45c946'
                }
              }]
            }
          }
        }],
        grid: {
          top: 0,
          left: 0,
          right: 0,
          bottom: 0
        }
      }
    }
  }
}
</script>

<style scoped lang="scss">
  .total-users-footer {
    display: flex;
    align-items: center;
  }

  .month {
    margin-left: 10px;
  }
</style>
