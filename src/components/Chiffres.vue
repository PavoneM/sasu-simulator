<template>
  <div class="container text-center">
    <div class="row">
      <div class="col-md-4">
        <span class="infos-chiffres">CHIFFRE D'AFFAIRES</span><br/>
        <span class="ca">{{ totalCa }} €</span><br/>
        <span class="ca-mois">{{ Math.floor(totalCa / 12) }} € / mois </span>
      </div>
      <div class="col-md-4">
        <span class="infos-chiffres">REVENUS NETS FREELANCE</span><br/>
        <span class="revenus">{{ totalRevenus }} €</span><br/>
        <span class="revenus-mois">{{ Math.floor(totalRevenus / 12) }} € / mois </span>
      </div>
      <div class="col-md-4">
        <span class="infos-chiffres">TAXES ET IMPÔTS</span><br/>
        <span class="impots">{{ totalTaxes }} €</span><br/>
        <span class="impots-mois">{{ Math.floor(totalTaxes / 12) }} € / mois </span>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Chiffres',
  props: {
    totalCa: Number,
    totalRevenus: Number,
    totalTaxes: Number
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

.container {
  margin-top: 50px;
}

.ca {
  color: #008ACF;
  font-size: 4rem;
}

.revenus {
  color: #21ba45;
  font-size: 4rem;
}

.impots {
  color: #db2828;
  font-size: 4rem;
}

.ca-mois {
  color: #008ACF;
  font-size: 1.5rem;
}

.revenus-mois {
  color: #21ba45;
  font-size: 1.5rem;
}

.impots-mois {
  color: #db2828;
  font-size: 1.5rem;
}

.infos-chiffres {
  font-size: 1rem;
  font-weight: 700;
  text-transform: uppercase;
}


</style>
