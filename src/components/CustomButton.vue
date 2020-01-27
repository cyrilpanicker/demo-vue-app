<template>
  <button v-on="$listeners">
    <slot/>
  </button>
</template>

<script>
export default {
  name: 'CustomButton'
}
</script>

<style lang="css" scoped>
  button{
    background-color: black;
    color: white;
    border: none;
    padding: 5px 10px;
    cursor: pointer;
  }
</style>
