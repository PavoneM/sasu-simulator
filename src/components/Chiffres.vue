<template>
  <div class="container text-center">
    <div class="row">
      <div class="col-md-4">
        <span class="ca">10 000€</span><br/>
        <span class="infos-chiffres">CHIFFRE D'AFFAIRES</span>
      </div>
      <div class="col-md-4">
        <span class="revenus">10 000€</span><br/>
        <span class="infos-chiffres">REVENUS NETS FREELANCE</span>
      </div>
      <div class="col-md-4">
        <span class="impots">10 000€</span><br/>
        <span class="infos-chiffres">TAXES ET IMPÔTS</span>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Chiffres',
  props: {

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

.infos-chiffres {
  font-size: 1rem;
  font-weight: 700;
  text-transform: uppercase;
}


</style>
