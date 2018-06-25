<template>
  <button
  class="el-button"
  :class = "[
    type? 'el-button--' + type : '',
    {'is-disabled': buttonDisabled,
    'is-loading': loading}
  ]"
  :disabled="buttonDisabled">
    <i class="el-icon-loading" v-if="loading"></i>
    <i v-if="icon&&!is-loading" :class="icon"></i>
    <slot></slot>
  </button>
</template>
<script>
export default {
  name: 'ElButton',
  props: {
    disabled: Boolean,
    type: {
      type: String,
      default: 'default'
    },
    loading: Boolean,
    icon: {
      type: String,
      default: ''
    }
  },
  computed: {
    buttonDisabled () {
      return this.disabled;
    }
  }
}  
</script>
<style>

</style>
