<!--
 * @Author: your name
 * @Date: 2020-10-20 17:06:27
 * @LastEditTime: 2020-10-21 09:26:30
 * @LastEditors: Please set LastEditors
 * @Description: In User Settings Edit
 * @FilePath: /flex-table/src/views/Home.vue
-->
<style scoped lang="sass">
.app_container
  .commodity
    display: flex

  .detail
    display: flex

</style>

<template lang="pug">
.app_container
  .commodity
    .title 商品规格:
    .content
      .commodity_list
        EachCommodity(
          v-for="item in commodityList"
          :key="item.id"
          :name.sync="item.name"
          :value.sync="item.value"
        )
      .commodity_settings
  .detail
    .title 规格明细:
    .content
      .detail_list
    el-table(
      :data="tableData"
      style="width: 100%"
    )
      el-table-column(
        prop="date"
        label="日期"
        width="180"
      )
      el-table-column(
        prop="name"
        label="姓名"
        width="180"
      )
      el-table-column(
        prop="address"
        label="地址"
      )
</template>

<script>
import Vue from 'vue'
import Component from 'vue-class-component'
import EachCommodity from '../components/EachCommodity'

@Component({
  components: {
    EachCommodity
  }
})

class Hello extends Vue {
  tableData = [{
    date: '2016-05-02',
    name: '王小虎',
    address: '上海市普陀区金沙江路 1518 弄'
  }, {
    date: '2016-05-04',
    name: '王小虎',
    address: '上海市普陀区金沙江路 1517 弄'
  }, {
    date: '2016-05-01',
    name: '王小虎',
    address: '上海市普陀区金沙江路 1519 弄'
  }, {
    date: '2016-05-03',
    name: '王小虎',
    address: '上海市普陀区金沙江路 1516 弄'
  }]

  commodityList = [
    {
      name: 'color',
      value: [
        'red',
        'grey',
        'red'
      ]
    },
    {
      name: 'size',
      value: [
        'small',
        'middle',
        'big'
      ]
    }
  ]
}

export default Hello
</script>
