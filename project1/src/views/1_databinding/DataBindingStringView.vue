<template>
<div>
  <h1>Hello {{ username }}</h1>
  <p>{{ message }}</p>
  <h2>{{ obj.kim }}</h2>
</div>
</template>

<script>
export default {
  data() {
    return {
      username: 'Hang',
      message: '김',
      arr: [],
      obj: {
        kim: 'kim'
      }
    }
  }
}
</script>

<style scoped>
.text-red {
  color: red;
}
</style>
