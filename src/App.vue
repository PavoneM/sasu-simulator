<template>
  <Header title="Simulateur SASU"/>
  <div class="container">

    <div class="infos">
      <div class="row">
        <div class="col-md-4">
          <ChiffreAffaireCard v-on:changeCA="onChangeCA"/>
        </div>
        <div class="col-md-4">
          <DepensesCard v-on:changeDepenses="onChangeDepenses" />
        </div>
        <div class="col-md-4">
          <RemunerationCard v-on:changeRemuneration="onChangeRemuneration"/>
        </div>
      </div>
    </div>

    <div class="chiffres">
      <Chiffres :totalCa="totalCa" :totalRevenus="totalRevenus" :totalTaxes="totalTaxes"/>
    </div>

    <div class="detailsChiffres">
      <DetailsChiffres :joursMois="joursMois"
                       :caTjm="caTjm"
                       :caAnnuel="caAnnuel"
                       :totalCa="totalCa"
                       :fraisMensuels="fraisMensuels"
                       :totalFrais="totalFrais"
                       :fraisAnnuels="fraisAnnuels"
                       :salaireBrutAnnuel="salaireBrutAnnuel"
                       :primeAnnuelle="primeAnnuelle"
                       :totalBrut="totalBrut"
                       :cotisationsPat="cotisationsPat"
                       :totalSuperBrut="totalSuperBrut"
                       :totalDepenses="totalDepenses"
                       :beneficeBrut="beneficeBrut"
                       :impotSociete="impotSociete"
                       :beneficeNet="beneficeNet"
                       :cotisationsSal="cotisationsSal"
                       :salaireNet="salaireNet"
                       :benefNet="benefNet"
                       :prelevSociaux="prelevSociaux"
                       :dividendes="dividendes"
                       :dividendesNets="dividendesNets"
                       :dividendesPourcent="dividendesPourcent"
                       :totalRevenus="totalRevenus"
      />
    </div>
  </div>
</template>

<script>

// Components
import Header from "@/components/Header";
import ChiffreAffaireCard from "@/components/ChiffreAffaireCard";
import DepensesCard from "@/components/DepensesCard";
import RemunerationCard from "@/components/RemunerationCard";
import Chiffres from "@/components/Chiffres";
import DetailsChiffres from "@/components/DetailsChiffres";

export default {
  data () {
    return {
      // From cards
      tjm: 0,
      joursMois: 0,
      autreMensuel: 0,
      autreAnnuel: 0,
      fraisMensuels: 0,
      fraisAnnuels: 0,
      salaireBrutMensuel: 0,
      primeAnnuelle: 0,
      dividendesPourcent: 0,

      // Computed Details
      caTjm: 0,
      caAnnuel: 0,
      totalCa: 0,
      totalFrais: 0,
      salaireBrutAnnuel: 0,
      totalBrut: 0,
      cotisationsPat: 0,
      totalSuperBrut: 0,
      totalDepenses: 0,
      beneficeBrut: 0,
      impotSociete: 0,
      beneficeNet: 0,
      cotisationsSal: 0,
      salaireNet: 0,
      benefNet: 0,
      prelevSociaux: 0,
      dividendes: 0,
      dividendesNets: 0,
      totalRevenus: 0,

      // Computed numbers
      totalTaxes: 0
    }
  },
  name: 'App',
  components: {
    Header,
    ChiffreAffaireCard,
    DepensesCard,
    RemunerationCard,
    Chiffres,
    DetailsChiffres
  },
  methods: {
    onChangeCA (value) {
      this.tjm = value.tjm;
      this.joursMois = value.joursMois;
      this.autreMensuel = value.autreMensuel;
      this.autreAnnuel = value.autreAnnuel;
    },
    onChangeDepenses (value) {
      this.fraisMensuels = value.fraisMensuels;
      this.fraisAnnuels = value.fraisAnnuels;
    },
    onChangeRemuneration (value) {
      this.salaireBrutMensuel = value.salaireBrutMensuel;
      this.primeAnnuelle = value.primeAnnuelle;
      this.dividendesPourcent = value.dividendesPourcent;
    },
    computeAllDetails () {

    }
  }
}
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}

.infos {
  margin-top: 30px;
}

</style>
