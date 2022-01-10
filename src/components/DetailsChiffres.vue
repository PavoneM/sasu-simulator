<template>
  <div class="container">
    <div class="card border-primary">
      <div class="card-header bg-primary text-white text-center">Détails</div>
      <div class="card-body">
        <div class="row">
          <div class="col-md-3">
            <div class="row">
              <div class="col-12"><b>Chiffre d'affaire</b></div>
              <div class="col-12">
                <table class="table table-borderless">
                  <tr>
                    <td>Jours travaillés / an</td>
                    <td class="text-end">0 €</td>
                  </tr>
                  <tr>
                    <td><br/></td>
                    <td></td>
                  </tr>
                  <tr>
                    <td>CA via TJM</td>
                    <td class="text-end">0 €</td>
                  </tr>
                  <tr>
                    <td>CA annuel</td>
                    <td class="text-end">0 €</td>
                  </tr>
                  <tr class="total">
                    <td><b>Total CA</b></td>
                    <td class="text-end"><b>0 €</b></td>
                  </tr>
                </table>
              </div>
            </div>
          </div>
          <div class="col-md-3">
            <div class="row">
              <div class="col-12"><b>Dépenses</b></div>
              <div class="col-12">
                <table class="table table-borderless">
                  <tr>
                    <td>Frais mensuels</td>
                    <td class="text-end">0 €</td>
                  </tr>
                  <tr>
                    <td>Frais annuels</td>
                    <td class="text-end">0 €</td>
                  </tr>
                  <tr class="total">
                    <td>Total frais</td>
                    <td class="text-end">0 €</td>
                  </tr>
                  <tr>
                    <td><br/></td>
                    <td></td>
                  </tr>
                  <tr>
                    <td>Salaire annuel brut</td>
                    <td class="text-end">0 €</td>
                  </tr>
                  <tr>
                    <td>Prime annuelle brute</td>
                    <td class="text-end">0 €</td>
                  </tr>
                  <tr class="total">
                    <td>Total brut</td>
                    <td class="text-end">0 €</td>
                  </tr>
                  <tr>
                    <td><br/></td>
                    <td></td>
                  </tr>
                  <tr>
                    <td>Cotis. patronales (42%)</td>
                    <td class="text-end">0 €</td>
                  </tr>
                  <tr class="total">
                    <td>Total super-brut</td>
                    <td class="text-end">0 €</td>
                  </tr>
                  <tr>
                    <td><br/></td>
                    <td></td>
                  </tr>
                  <tr>
                    <td><b>Total dépenses</b></td>
                    <td class="text-end"><b>0 €</b></td>
                  </tr>
                </table>
              </div>
            </div>
          </div>
          <div class="col-md-3">
            <div class="row">
              <div class="col-12"><b>Bénéfices</b></div>
              <div class="col-12">
                <table class="table table-borderless">
                  <tr>
                    <td>Total CA</td>
                    <td class="text-end">0 €</td>
                  </tr>
                  <tr>
                    <td>Total Dépenses</td>
                    <td class="text-end">0 €</td>
                  </tr>
                  <tr class="total">
                    <td>Bénéfice brut</td>
                    <td class="text-end">0 €</td>
                  </tr>
                  <tr>
                    <td><br/></td>
                    <td></td>
                  </tr>
                  <tr>
                    <td>Impôt sur les Sociétés (IS)</td>
                    <td class="text-end">0 €</td>
                  </tr>
                  <tr class="total">
                    <td><b>Bénéfice net</b></td>
                    <td class="text-end"><b>0 €</b></td>
                  </tr>
                </table>
              </div>
            </div>
          </div>
          <div class="col-md-3">
            <div class="row">
              <div class="col-12"><b>Revenus</b></div>
              <div class="col-12">
                <table class="table table-borderless">
                  <tr>
                    <td>Salaire brut</td>
                    <td class="text-end">0 €</td>
                  </tr>
                  <tr>
                    <td>Cotis. salariales (22%)</td>
                    <td class="text-end">0 €</td>
                  </tr>
                  <tr class="total">
                    <td>Salaire net</td>
                    <td class="text-end">0 €</td>
                  </tr>
                  <tr>
                    <td><br/></td>
                    <td></td>
                  </tr>
                  <tr>
                    <td>Bénéfice net</td>
                    <td class="text-end">0 €</td>
                  </tr>
                  <tr>
                    <td>Dividendes versés</td>
                    <td class="text-end">0 €</td>
                  </tr>
                  <tr>
                    <td>Prélévements sociaux (15.5%)</td>
                    <td class="text-end">0 €</td>
                  </tr>
                  <tr class="total">
                    <td>Dividendes nets</td>
                    <td class="text-end">0 €</td>
                  </tr>
                  <tr>
                    <td><br/></td>
                    <td></td>
                  </tr>
                  <tr>
                    <td><b>Total revenus</b></td>
                    <td class="text-end"><b>0 €</b></td>
                  </tr>
                </table>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'DetailsChiffres',
  props: {

  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

.container {
  margin-top: 50px;
}

.card-header {
  padding: 5px;
}

td {
  padding: 0px !important;
  font-size: 14px;
}

.table {
  margin-top: 5px;
}

tr.total {
  border-top: 1px solid #9f9d9d !important;
}

</style>
