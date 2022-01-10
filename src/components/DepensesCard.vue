<template>
  <div class="card border-primary">
    <div class="card-header bg-primary text-white text-center">Dépenses</div>
    <div class="card-body">
      <div class="mb-3">
        <label for="fraismensuels" class="form-label">Frais mensuels</label>
        <input id="fraismensuels" type="number" class="form-control" step="10" placeholder="0" v-model="fraisMensuels" v-on:change="changeDepenses" />
      </div>
      <div class="mb-3">
        <label for="fraisannuels" class="form-label">Frais annuels</label>
        <input id="fraisannuels" type="number" class="form-control" step="100" placeholder="0" v-model="fraisAnnuels" v-on:change="changeDepenses" />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      fraisMensuels: 0,
      fraisAnnuels: 0
    }
  },
  name: 'DepensesCard',
  props: {

  },
  methods: {
    changeDepenses () {
      this.$emit('changeDepenses', {fraisMensuels: this.fraisMensuels, fraisAnnuels: this.fraisAnnuels})
    }
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
