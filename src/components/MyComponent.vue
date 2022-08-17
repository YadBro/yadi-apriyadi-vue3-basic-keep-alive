<template>
  <p>{{text}}</p>
</template>

<script>
  export default {
    props: {
      text: {
        type: String,
        default: '',
        required: true,
      }
    }
  }
</script>