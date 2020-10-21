<!--
 * @Author: your name
 * @Date: 2020-10-20 17:18:43
 * @LastEditTime: 2020-10-21 09:48:54
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
    input(:value="name" @input="$emit('update:name', $event.target.value)")
  .prop_value
    span 规格值
    .value_list
      input.value_input(
        v-for="item, index in value"
        :key="index"
        :value="item"
        @input="updateValueList($event, item, index)"
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
  updateValueList (event, item, index) {
    const value = event.target.value
    this.value.splice(index, 1, value)
    this.$emit('update:value', this.value)
  }
}

export default EachCommodity
</script>
