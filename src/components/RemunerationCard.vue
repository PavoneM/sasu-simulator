<template>
  <div class="card border-primary">
    <div class="card-header bg-primary text-white text-center">Rémunération</div>
    <div class="card-body">
      <div class="mb-3">
        <label for="brutannuel" class="form-label">Salaire mensuel brut</label>
        <input id="brutannuel" type="number" class="form-control" step="100" min="0" placeholder="0" v-model="salaireBrutMensuel" v-on:keyup="changeRemuneration" v-on:change="changeRemuneration" />
      </div>
      <div class="mb-3">
        <label for="primeannuelle" class="form-label">Prime annuelle</label>
        <input id="primeannuelle" type="number" class="form-control" step="100" min="0" placeholder="0" v-model="primeAnnuelle" v-on:keyup="changeRemuneration" v-on:change="changeRemuneration" />
      </div>
      <div class="mb-3">
        <label for="dividendespris" class="form-label">Dividendes pris (%)</label>
        <input id="dividendespris" type="number" class="form-control" step="1" min="0" placeholder="0" v-model="dividendesPourcent" v-on:keyup="changeRemuneration" v-on:change="changeRemuneration" />
      </div>
      <div class="mb-3">
        <label for="reductionIr" class="form-label">Réduction d'IR</label>
        <input id="reductionIr" type="number" class="form-control" step="100" min="0" placeholder="0" v-model="reductionIr" v-on:keyup="changeRemuneration" v-on:change="changeRemuneration" />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      salaireBrutMensuel: 1500,
      primeAnnuelle: 0,
      dividendesPourcent: 80,
      reductionIr: 0
    }
  },
  name: 'RemunerationCard',
  props: {

  },
  methods: {
    changeRemuneration () {
      this.$emit('changeRemuneration', {
        salaireBrutMensuel: Math.floor(this.salaireBrutMensuel),
        primeAnnuelle: Math.floor(this.primeAnnuelle),
        dividendesPourcent: Math.floor(this.dividendesPourcent),
        reductionIr: Math.floor(this.reductionIr)
      })
    }
  },
  beforeMount(){
    this.changeRemuneration();
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
