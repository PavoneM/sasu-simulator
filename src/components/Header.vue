<template>
  <nav class="navbar navbar-light bg-light justify-content-center text-center">
    <div class="row logo-container">
      <div class="col-xs-12">
        <img class="logo" alt="MP logo" src="@/assets/logo.png">
      </div>
      <div class="col-xs-12">
        <h3 class="title">{{ title }}</h3>
      </div>
    </div>
  </nav>
</template>

<script>
export default {
  name: 'Header',
  props: {
    title: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

.banner {
  height: 10em;
  max-height: 16em;
}

.logo {
  height: 50px;
}

.title {
  margin-bottom: 0px;
}
</style>
