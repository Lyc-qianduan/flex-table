<!--
 * @Author: your name
 * @Date: 2020-10-20 17:06:27
 * @LastEditTime: 2020-10-20 17:38:27
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
          :name="item.name"
          :value="item.value"
        )
      .commodity_settings
  .detail
    .title 规格明细:
    .content
      .detail_list list

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
