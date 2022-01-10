<template>
  <div class="card border-primary">
    <div class="card-header bg-primary text-white text-center">Chiffre d'affaire</div>
    <div class="card-body">
      <div class="mb-3">
        <label for="tjm" class="form-label">Journalier (TJM)</label>
        <input id="tjm" type="number" class="form-control" step="10" placeholder="0" v-model="tjm" v-on:change="changeCA"/>
      </div>
      <div class="mb-3">
        <label for="joursmois" class="form-label">Jours / mois</label>
        <input id="joursmois" type="number" class="form-control" step="1" placeholder="0" v-model="joursMois" v-on:change="changeCA"/>
      </div>
      <div class="mb-3">
        <label for="autremensuel" class="form-label">Autre mensuel</label>
        <input id="autremensuel" type="number" class="form-control" step="100" placeholder="0" v-model="autreMensuel" v-on:change="changeCA"/>
      </div>
      <div class="mb-3">
        <label for="autreannuel" class="form-label">Autre annuel</label>
        <input id="autreannuel" type="number" class="form-control" step="100" placeholder="0" v-model="autreAnnuel" v-on:change="changeCA"/>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      tjm: 0,
      joursMois: 0,
      autreMensuel: 0,
      autreAnnuel: 0
    }
  },
  name: 'CaCard',
  props: {
  },
  methods: {
    changeCA () {
      this.$emit('changeCA', {tjm: this.tjm, joursMois: this.joursMois, autreMensuel: this.autreMensuel, autreAnnuel: this.autreAnnuel})
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
