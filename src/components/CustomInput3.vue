<template>
  <label>
    <div>{{label}}</div>
    <input :value="value" @input="$emit('update:value', $event.target.value)" />
  </label>
</template>

<script>
export default {
  name: 'CustomInput3',
  props: ['value', 'label']
}
</script>
