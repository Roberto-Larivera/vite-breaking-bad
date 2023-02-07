<script>
export default {
  name: 'FoundCard',
  data() {
    return {

    }
  },
  props:{
    myNumber:{
      type: Number,
      default: 0
    }
  }

}
</script>

<template>
  <div>
    <h3>
      Found <span>{{ myNumber }}</span> character
    </h3>
  </div>
</template>

<style lang="scss" scoped>
span{
  color: $color_b;
}
</style>
