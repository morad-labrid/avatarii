<template>
  <div class="w-full h-full">
    <div class="w-full h-full bg-gray-400 rounded-full"></div>
  </div>
</template>
<script>
export default {
  name: 'EyesType',
  props: {
    color: { type: String, default: 'black' },
  },
}
</script>
<style>
svg {
  width: 100%;
  height: 100%;
}
</style>
