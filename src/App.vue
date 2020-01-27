<template>
  <div id="app">

    <BlogPost
      :post="blogPost.post"
      :font-size="blogPost.fontSize"
      @font-size-inc="blogPost.fontSize += 0.1"
      @font-size-dec="blogPost.fontSize -= 0.1"
    />
    <hr/>

    <CustomButton @click="onCustomButtonClick">
      click here
    </CustomButton>
    <hr/>

    <CustomInput
      :value="customInput.value" @input="customInput.value = $event"
      :label="customInput.label"
    />
    <div>{{customInput.value}}</div>
    <hr/>

    <CustomInput
      v-model="customInput.value"
      :label="customInput.label"
    />
    <div>{{customInput.value}}</div>
    <hr/>

    <CustomInput2
      v-model="customInput.value"
      :label="customInput.label"
      :placeholder="customInput.placeholder"
      @focus="onCustomInputFocus"
      @blur="onCustomInputBlur"
    />
    <div>{{customInput.value}}</div>
    <hr/>

    <CustomInput3
      :value.sync="customInput.value"
      :label="customInput.label"
    />
    <div>{{customInput.value}}</div>
    <hr/>

    <CustomCheckbox :checked="customCheckbox.checked" @change="customCheckbox.checked = $event" />
    {{customCheckbox.checked}}
    <hr/>

    <CustomCheckbox v-model="customCheckbox.checked" />
    {{customCheckbox.checked}}
    <hr/>

  </div>
</template>

<script>
import BlogPost from './components/BlogPost';
import CustomInput from './components/CustomInput';
import CustomInput2 from './components/CustomInput2';
import CustomInput3 from './components/CustomInput3';
import CustomButton from './components/CustomButton';
import CustomCheckbox from './components/CustomCheckbox';

export default {
  name: 'app',
  components: {
    BlogPost,
    CustomInput,
    CustomInput2,
    CustomInput3,
    CustomButton,
    CustomCheckbox
  },
  data () {
    return {
      blogPost: {
        fontSize: 1,
        post: {
          title: 'title',
          content: 'content'
        }
      },
      customInput: {
        value: 'sample text',
        label: 'sample label',
        placeholder: 'sample placeholder'
      },
      customCheckbox: {
        checked: true
      }
    };
  },
  computed: {
  },
  methods: {
    onCustomButtonClick () {
      alert('button clicked');
    },
    onCustomInputFocus () {
      console.log('focused');
    },
    onCustomInputBlur () {
      console.log('blured');
    }
  }
};
</script>

<style>
/* #app {
} */
</style>
