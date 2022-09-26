<template>
  <li>
    <input type="checkbox" v-model="checked">
    <slot name="ant-error" v-bind="{checked: checked}"></slot>
  </li>
</template>

<script>
export default {
  props: ['item'],
  data() {
    return {
        checked: false
    }
  }
}
</script>
<style></style>