<template>
  <div class="cropper">
    <vueCropper
      ref="cropper"
      :img="option.img"
      :outputSize="option.size"
      :outputType="option.outputType"
    ></vueCropper>
  </div>
</template>

<script>
export default {
  props: ["option"],
};
</script>

<style lang="scss" scoped>
.cropper {
  width: 500px;
  height: 500px;
}
</style>
