<template>
  <div class="card border-primary">
    <div class="card-header bg-primary text-white text-center">Rémunération</div>
    <div class="card-body">
      <div class="mb-3">
        <label for="brutannuel" class="form-label">Salaire mensuel brut</label>
        <input id="brutannuel" type="number" class="form-control" step="100" placeholder="0" v-model="salaireBrutMensuel" v-on:change="changeRemuneration" />
      </div>
      <div class="mb-3">
        <label for="primeannuelle" class="form-label">Prime annuelle</label>
        <input id="primeannuelle" type="number" class="form-control" step="100" placeholder="0" v-model="primeAnnuelle" v-on:change="changeRemuneration" />
      </div>
      <div class="mb-3">
        <label for="dividendespris" class="form-label">Dividendes pris (%)</label>
        <input id="dividendespris" type="number" class="form-control" step="1" placeholder="0" v-model="dividendesPourcent" v-on:change="changeRemuneration" />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      salaireBrutMensuel: 0,
      primeAnnuelle: 0,
      dividendesPourcent: 0
    }
  },
  name: 'RemunerationCard',
  props: {

  },
  methods: {
    changeRemuneration () {
      this.$emit('changeRemuneration', {salaireBrutMensuel: this.salaireBrutMensuel, primeAnnuelle: this.primeAnnuelle, dividendesPourcent: this.dividendesPourcent})
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
