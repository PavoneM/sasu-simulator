<template>
  <div class="container">
    <div class="card border-primary">
      <div class="card-header bg-primary text-white text-center">Détails</div>
      <div class="card-body">
        <div class="row">
          <div class="col-md-3">
            <div class="row">
              <div class="col-12 fw-bold">Chiffre d'affaire</div>
              <div class="col-12">
                <table class="table table-borderless">
                  <tr>
                    <td>Jours travaillés / an</td>
                    <td class="text-end">{{ joursMois * 12 }}</td>
                  </tr>
                  <tr>
                    <td><br/></td>
                    <td></td>
                  </tr>
                  <tr>
                    <td>CA via TJM</td>
                    <td class="text-end">{{ caTjm }} €</td>
                  </tr>
                  <tr>
                    <td>CA mensuel (autre)</td>
                    <td class="text-end">{{ caMensuel }} €</td>
                  </tr>
                  <tr>
                    <td>CA annuel (autre)</td>
                    <td class="text-end">{{ caAnnuel }} €</td>
                  </tr>
                  <tr class="total">
                    <td>Total CA</td>
                    <td class="text-end">{{ totalCa }} €</td>
                  </tr>
                </table>
              </div>
            </div>
          </div>
          <div class="col-md-3">
            <div class="row">
              <div class="col-12 fw-bold">Dépenses</div>
              <div class="col-12">
                <table class="table table-borderless">
                  <tr>
                    <td>Frais mensuels</td>
                    <td class="text-end">{{ totalFraisMensuels }} €</td>
                  </tr>
                  <tr>
                    <td>Frais annuels</td>
                    <td class="text-end">{{ fraisAnnuels }} €</td>
                  </tr>
                  <tr class="total">
                    <td>Total frais</td>
                    <td class="text-end">{{ totalFrais }} €</td>
                  </tr>
                  <tr>
                    <td><br/></td>
                    <td></td>
                  </tr>
                  <tr>
                    <td>Salaire annuel brut</td>
                    <td class="text-end">{{ salaireBrutAnnuel }} €</td>
                  </tr>
                  <tr>
                    <td>Prime annuelle brute</td>
                    <td class="text-end">{{ primeAnnuelle }} €</td>
                  </tr>
                  <tr class="total">
                    <td>Total brut</td>
                    <td class="text-end">{{ totalBrut }} €</td>
                  </tr>
                  <tr>
                    <td><br/></td>
                    <td></td>
                  </tr>
                  <tr>
                    <td>Cotis. patronales (42%)</td>
                    <td class="text-end">{{ cotisationsPat }} €</td>
                  </tr>
                  <tr class="total">
                    <td>Total super-brut</td>
                    <td class="text-end">{{ totalSuperBrut }} €</td>
                  </tr>
                  <tr>
                    <td><br/></td>
                    <td></td>
                  </tr>
                  <tr class="fw-bold">
                    <td>Total dépenses</td>
                    <td class="text-end">{{ totalDepenses }} €</td>
                  </tr>
                </table>
              </div>
            </div>
          </div>
          <div class="col-md-3">
            <div class="row">
              <div class="col-12 fw-bold">Bénéfices</div>
              <div class="col-12">
                <table class="table table-borderless">
                  <tr>
                    <td>Total CA</td>
                    <td class="text-end">{{ totalCa }} €</td>
                  </tr>
                  <tr>
                    <td>Total Dépenses</td>
                    <td class="text-end">{{ totalDepenses }} €</td>
                  </tr>
                  <tr class="total">
                    <td>Bénéfice brut</td>
                    <td class="text-end">{{ beneficeBrut }} €</td>
                  </tr>
                  <tr>
                    <td><br/></td>
                    <td></td>
                  </tr>
                  <tr>
                    <td>Impôt sur les Sociétés (IS)</td>
                    <td class="text-end">{{ impotSociete }} €</td>
                  </tr>
                  <tr class="total">
                    <td>Bénéfice net</td>
                    <td class="text-end">{{ beneficeNet }} €</td>
                  </tr>
                </table>
              </div>
            </div>
          </div>
          <div class="col-md-3">
            <div class="row">
              <div class="col-12 fw-bold">Revenus</div>
              <div class="col-12">
                <table class="table table-borderless">
                  <tr>
                    <td>Salaire brut</td>
                    <td class="text-end">{{ salaireBrutAnnuel }} €</td>
                  </tr>
                  <tr>
                    <td>Cotis. salariales (22%)</td>
                    <td class="text-end">{{ cotisationsSal }} €</td>
                  </tr>
                  <tr class="total">
                    <td>Salaire net</td>
                    <td class="text-end">{{ salaireNet }} €</td>
                  </tr>
                  <tr>
                    <td><br/></td>
                    <td></td>
                  </tr>
                  <tr>
                    <td>Salaire net imposable</td>
                    <td class="text-end">{{ salaireNetImposable }} €</td>
                  </tr>
                  <tr>
                    <td>Impot sur le revenu</td>
                    <td class="text-end">{{ impotRevenu }} €</td>
                  </tr>
                  <tr>
                    <td>Reduction d'IR</td>
                    <td class="text-end">{{ reductionIr }} €</td>
                  </tr>
                  <tr class="total">
                    <td>Salaire net après impôts</td>
                    <td class="text-end">{{ salaireNetImpot }} €</td>
                  </tr>
                  <tr>
                    <td><br/></td>
                    <td></td>
                  </tr>
                  <tr>
                    <td>Bénéfice net</td>
                    <td class="text-end">{{ beneficeNet }} €</td>
                  </tr>
                  <tr>
                    <td>Dividendes versés ({{ dividendesPourcent }} %)</td>
                    <td class="text-end">{{ dividendes }} €</td>
                  </tr>
                  <tr>
                    <td>Flat tax (30%)</td>
                    <td class="text-end">{{ prelevSociaux }} €</td>
                  </tr>
                  <tr class="total">
                    <td>Dividendes nets</td>
                    <td class="text-end">{{ dividendesNets }} €</td>
                  </tr>
                  <tr>
                    <td><br/></td>
                    <td></td>
                  </tr>
                  <tr class="fw-bold">
                    <td>Total revenus</td>
                    <td class="text-end">{{ totalRevenus }} €</td>
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
    joursMois: Number,
    caTjm: Number,
    caAnnuel: Number,
    caMensuel: Number,
    totalCa: Number,
    totalFraisMensuels: Number,
    fraisAnnuels: Number,
    totalFrais: Number,
    salaireBrutAnnuel: Number,
    primeAnnuelle: Number,
    totalBrut: Number,
    cotisationsPat: Number,
    totalSuperBrut: Number,
    totalDepenses: Number,
    beneficeBrut: Number,
    impotSociete: Number,
    beneficeNet: Number,
    cotisationsSal: Number,
    salaireNet: Number,
    dividendes: Number,
    prelevSociaux: Number,
    dividendesPourcent: Number,
    dividendesNets: Number,
    salaireNetImposable: Number,
    impotRevenu: Number,
    reductionIr: Number,
    salaireNetImpot: Number,
    totalRevenus: Number
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
  font-weight: bold;
}

</style>
