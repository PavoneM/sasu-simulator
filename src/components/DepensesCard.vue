<template>
  <div class="card border-primary">
    <div class="card-header bg-primary text-white text-center">Dépenses</div>
    <div class="card-body">
      <div class="mb-3">
        <label for="fraismensuels" class="form-label">Frais mensuels</label>
        <input id="fraismensuels" type="number" class="form-control" step="100" placeholder="0"/>
      </div>
      <div class="mb-3">
        <label for="fraisannuels" class="form-label">Frais annuels</label>
        <input id="fraisannuels" type="number" class="form-control" step="100" placeholder="0"/>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'DepensesCard',
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
