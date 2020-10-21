<!--
 * @Author: your name
 * @Date: 2020-10-20 17:06:27
 * @LastEditTime: 2020-10-21 10:30:11
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
        v-for="item in columnsList"
        :key="item.id"
        :label="item.prop"
        :prop="item.prop"
        width="180"
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
  columnsList = [
    {
      prop: 'color'
    },
    {
      prop: 'size'
    },
    {
      prop: 'price'
    },
    {
      prop: 'stock'
    },
    {
      prop: 'weight'
    },
    {
      prop: 'code'
    },
    {
      prop: 'rawCost'
    }
  ]

  tableData = [
    {
      color: 'red',
      size: 'middle',
      price: 998,
      stock: 9,
      weight: 9,
      code: 990,
      rawCost: 9
    },
    {
      color: 'red',
      size: 'middle',
      price: 998,
      stock: 9,
      weight: 9,
      code: 990,
      rawCost: 9
    }
  ]

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
