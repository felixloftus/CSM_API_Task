<template>
  <div class="cloudy">
      <p>hhi</p>
      {{description}}
</div>
</template>

<style lang="scss" scoped>
#cloudy{
    font-family: 'Courier New', Courier, monospace;
}
</style>
<script>
export default {
 props: ['description']
}
</script>