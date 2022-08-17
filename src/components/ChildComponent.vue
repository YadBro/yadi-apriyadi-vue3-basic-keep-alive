<template>
  <h1>{{veryTitle}}</h1>
  <div>Title</div>
  <slot :data="{title}"/>
  
  <div>Content</div>
  <slot name="content" :data="{content}"/>
  
  <div>Footer</div>
  <slot name="footer" :data="{footer}"/>
</template>

<script>
  export default {
    data() {
      return {
        title: 'title',
        content: 'content',
        footer: 'footer',
      }
    },
    props: {
      veryTitle: {
        type: String,
        required: true,
        default: 'Hello',
        validator(value) {
          return ['World'].includes(value);
        }
      }
    }
  }
</script>