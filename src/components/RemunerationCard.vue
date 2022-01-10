<template>
  <div class="card border-primary">
    <div class="card-header bg-primary text-white text-center">Rémunération</div>
    <div class="card-body">
      <div class="mb-3">
        <label for="brutannuel" class="form-label">Salaire mensuel brut</label>
        <input id="brutannuel" type="number" class="form-control" step="100" placeholder="0"/>
      </div>
      <div class="mb-3">
        <label for="primeannuelle" class="form-label">Prime annuelle</label>
        <input id="primeannuelle" type="number" class="form-control" step="100" placeholder="0"/>
      </div>
      <div class="mb-3">
        <label for="dividendespris" class="form-label">Dividendes pris</label>
        <input id="dividendespris" type="number" class="form-control" step="100" placeholder="0"/>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'RemunerationCard',
  props: {

  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

.card-header {
  padding: 5px;
}

.card {
  height: 100%;
}

</style>
