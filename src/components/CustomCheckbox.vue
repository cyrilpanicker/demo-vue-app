<template>
  <input type="checkbox" :checked="checked" @change="$emit('change',$event.target.checked)" />
</template>

<script>
export default {
  name: 'CustomCheckbox',
  props: ['checked'],
  model: {
    prop: 'checked',
    event: 'change'
  }
}
</script>
