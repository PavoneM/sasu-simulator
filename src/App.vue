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
                       :caMensuel="caMensuel"
                       :caAnnuel="caAnnuel"
                       :totalCa="totalCa"
                       :totalFraisMensuels="totalFraisMensuels"
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
                       :salaireNetImposable="salaireNetImposable"
                       :impotRevenu="impotRevenu"
                       :reductionIr="reductionIr"
                       :salaireNetImpot="salaireNetImpot"
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
      salaireNetImposable: 0,
      impotRevenu: 0,
      reductionIr: 0,
      salaireNetImpot: 0,

      // Computed Details
      caTjm: 0,
      caMensuel: 0,
      caAnnuel: 0,
      totalCa: 0,
      totalFraisMensuels: 0,
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
      this.computeAllDetails();
    },
    onChangeDepenses (value) {
      this.fraisMensuels = value.fraisMensuels;
      this.fraisAnnuels = value.fraisAnnuels;
      this.computeAllDetails();
    },
    onChangeRemuneration (value) {
      this.salaireBrutMensuel = value.salaireBrutMensuel;
      this.primeAnnuelle = value.primeAnnuelle;
      this.dividendesPourcent = value.dividendesPourcent;
      this.reductionIr = value.reductionIr;
      this.computeAllDetails();
    },
    computeAllDetails () {
      this.caTjm = this.tjm * this.joursMois * 12;
      this.caMensuel = this.autreMensuel * 12;
      this.caAnnuel = this.autreAnnuel;
      this.totalCa = this.caTjm + this.caMensuel + this.caAnnuel;
      this.totalFraisMensuels = this.fraisMensuels * 12;
      this.totalFrais = this.totalFraisMensuels + this.fraisAnnuels;
      this.salaireBrutAnnuel = this.salaireBrutMensuel * 12;
      this.cotisationsSal = Math.floor(this.salaireBrutAnnuel * 0.22);
      this.salaireNet = this.salaireBrutAnnuel - this.cotisationsSal;
      this.totalBrut = this.salaireBrutAnnuel + this.primeAnnuelle;
      this.cotisationsPat = Math.floor(this.totalBrut * 0.42);
      this.totalSuperBrut = this.totalBrut + this.cotisationsPat;
      this.totalDepenses = this.totalSuperBrut + this.totalFrais;
      this.beneficeBrut = this.totalCa - this.totalDepenses;

      const tranche1IS = 38120;
      if (this.beneficeBrut >= 0 ) {
        if (this.beneficeBrut <= tranche1IS) {
          this.impotSociete = Math.floor(this.beneficeBrut * 0.15);
        } else {
          this.impotSociete = Math.floor(tranche1IS * 0.15 + (this.beneficeBrut - tranche1IS) * 0.25);
        }
      }
      this.beneficeNet = this.beneficeBrut - this.impotSociete;

      const trancheIR1 = 10225;
      const trancheIR2 = 26070;
      const trancheIR3 = 74545;
      const trancheIR4 = 160336;

      // 2022 https://www.corrigetonimpot.fr/decote-impot-revenu-calcul-declaration/

      // const csg = this.salaireNet * 0.024;
      // const crds = this.salaireNet * 0.05;
      // Le salaire imposable s'obtient en additionnant  au salaire net la part de charges sociales non déductible calculée soit : 2,40 % de 98,25 % du salaire brut.
      this.salaireNetImposable = Math.floor( this.salaireNet + this.salaireBrutAnnuel * 0.9825 * 0.024);

      // Abattement 10%
      this.salaireNetImposable = Math.floor(this.salaireNetImposable * 0.9);

      if (this.salaireNetImposable >= 0 ) {
        if (this.salaireNetImposable <= trancheIR1) {
          this.impotRevenu = 0;
        } else if (this.salaireNetImposable <= trancheIR2) {
          this.impotRevenu = Math.floor((this.salaireNetImposable - trancheIR1) * 0.11);
        } else if (this.salaireNetImposable <= trancheIR3) {
          this.impotRevenu = Math.floor((trancheIR2 - trancheIR1) * 0.11 + (this.salaireNetImposable - trancheIR2) * 0.30);
        } else if (this.salaireNetImposable <= trancheIR4) {
          this.impotRevenu = Math.floor((trancheIR2 - trancheIR1) * 0.11 + (trancheIR3 - trancheIR2) * 0.30 + (this.salaireNetImposable - trancheIR3) * 0.41);
        }
      }

      // Calcul de la décôte éventuelle si < 1746 €
      if (this.salaireNetImposable < (1746*12)) {
        this.impotRevenu -= Math.floor(790 - 0.4525 * this.impotRevenu);
      }
      if (this.impotRevenu < 0) {
        this.impotRevenu = 0;
      }

      this.salaireNetImpot = this.salaireNet - this.impotRevenu + this.reductionIr;

      this.dividendes = Math.ceil(this.dividendesPourcent/100  * this.beneficeNet);
      this.prelevSociaux = Math.floor(this.dividendes * 0.3);
      this.dividendesNets = this.dividendes - this.prelevSociaux;

      this.totalRevenus = this.salaireNetImpot + this.dividendesNets;
      this.totalTaxes = this.impotSociete + this.cotisationsPat + this.cotisationsSal + this.prelevSociaux + this.impotRevenu;
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
