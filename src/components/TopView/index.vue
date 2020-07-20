<template>
  <div class="top-view">
    <el-row :gutter="20">
      <el-col :span="6">
        <total-sales/>
      </el-col>
      <el-col :span="6">
        <total-orders/>
      </el-col>
      <el-col :span="6">
        <today-users/>
      </el-col>
      <el-col :span="6">
        <total-users/>
      </el-col>
    </el-row>
  </div>
</template>

<script>
import TotalSales from '../TotalSales'
import TotalOrders from '../TotalOrders'
import TodayUsers from '../TodayUsers'
import TotalUsers from '../TotalUsers'

export default {
  name: 'index',
  components: {
    TotalSales,
    TotalOrders,
    TodayUsers,
    TotalUsers
  }
}
</script>

<style lang="scss" scoped>

</style>
