<template>
  <label>
    <div>{{label}}</div>
    <input :value="value" @input="$emit('input', $event.target.value)" />
  </label>
</template>

<script>
export default {
  name: 'CustomInput',
  props: ['value', 'label']
}
</script>
