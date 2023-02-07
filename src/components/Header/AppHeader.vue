<script>
export default {
  name: 'AppHeader',
  data() {
    return {

    }
  }

}
</script>

<template>
  <header>
    <div class="container">
      <div class="row">
        <div class="col d-flex">
          <div class="logo-header d-flex align-items-center me-3">
            <img class="w-100" src="../../assets/logo.webp" alt="logo">
          </div>
          <div>
            <h1>Yu-Gi-oh!</h1>
          </div>
        </div>
      </div>
    </div>
  </header>
</template>

<style lang="scss" scoped>
header{
  background-color: $color_light-b;
  h1{
    color:$color_dark;
  }
  .logo-header{
  width: 100px;
}
}
</style>
