<template>
  <div class="blog-post" :style="{ 'font-size': fontSize+'em' }">
    <h3>
      {{post.title}}
      <button @click="$emit('font-size-inc')">+</button>
      <button @click="$emit('font-size-dec')">-</button>
    </h3>
    <div>{{post.content}}</div>
  </div>
</template>

<script>
export default {
  name: 'BlogPost',
  props: ['post', 'fontSize']
}
</script>
