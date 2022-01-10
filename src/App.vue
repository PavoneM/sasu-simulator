<template>
  <Header title="Simulateur SASU"/>
  <div class="container">
    <div class="infos">
      <div class="row">
        <div class="col-md-4">
          <ChiffreAffaireCard/>
        </div>
        <div class="col-md-4">
          <DepensesCard/>
        </div>
        <div class="col-md-4">
          <RemunerationCard/>
        </div>
      </div>
    </div>
  </div>
</template>

<script>

// Components
import Header from "@/components/Header";
import ChiffreAffaireCard from "@/components/ChiffreAffaireCard";
import DepensesCard from "@/components/DepensesCard";
import RemunerationCard from "@/components/RemunerationCard";

export default {
  name: 'App',
  components: {
    Header,
    ChiffreAffaireCard,
    DepensesCard,
    RemunerationCard
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
