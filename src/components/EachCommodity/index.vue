<!--
 * @Author: your name
 * @Date: 2020-10-20 17:18:43
 * @LastEditTime: 2020-10-20 17:39:53
 * @LastEditors: Please set LastEditors
 * @Description: In User Settings Edit
 * @FilePath: /flex-table/src/components/EachCommodity.vue
-->
<style scoped lang="sass">
.each_commodity
  .prop_name
    text-align: left

  .prop_value
    display: flex
</style>

<template lang="pug">
.each_commodity
  .prop_name
    span 规格名
    input(:value="name")
  .prop_value
    span 规格值
    .value_list
      input.value_input(
        v-for="item, index in value"
        :key="index"
        :value="item"
      )
</template>

<script>
import Vue from 'vue'
import Component from 'vue-class-component'

@Component({
  props: {
    name: String,
    value: Array
  }
})
class EachCommodity extends Vue {
}

export default EachCommodity
</script>
