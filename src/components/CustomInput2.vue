<template>
  <label>
    <div>{{label}}</div>
    <input v-bind="$attrs" :value="value" v-on="listeners" />
  </label>
</template>

<script>
export default {
  name: 'CustomInput2',
  props: ['value', 'label'],
  inheritAttrs: false,
  computed: {
    listeners () {
      return {
        ...this.$listeners,
        input: (event) => this.$emit('input', event.target.value)
      };
    }
  }
}
</script>
