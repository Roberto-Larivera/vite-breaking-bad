<script>
export default {
  name: 'LoadingSpinner',
  data() {
    return {

    }
  }

}
</script>

<template>
  <div class="d-flex justify-content-center align-items-center h-100">
    <div class="spinner-grow" style="width: 5rem; height: 5rem;" role="status">
      <span class="visually-hidden">Loading...</span>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.spinner-grow{
  color: $color_b;
}
</style>
