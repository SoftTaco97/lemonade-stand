<template>
  <div id="app">
    <!-- appHeader -->
    <appHeader />

    <!-- main -->
    <main>
      <md-content class="md-elevation-1">
        <div class="md-layout md-gutter md-alignment-center-center">
          <app-stats-key />
          <app-stats :total=total :employees=employees :managers=managers />
          <app-options-key />
          <app-options :cupPrice=cupPrice :employeeCost=employeeCost :managerCost=managerCost />
        </div>
      </md-content>
    </main>
    <!-- end main -->

    <!-- appFooter -->
    <appFooter />
  </div>
</template>

<script>

// Components
import appHeader from './components/Header.vue';
import appFooter from './components/Footer.vue';
import appStatsKey from './components/StatsKey.vue';
import appStats from './components/Stats.vue';
import appOptionsKey from './components/OptionsKey.vue';
import appOptions from './components/Options.vue';

export default {
  name: 'app',
  data() {
    return {
      total: 0.00,
      employees: 0,
      managers: 0,
      employeeCost: 200,
      managerCost: 1000,
      cupPrice: 10
    }
  },
  methods: {
    soldCup(){
      this.total += this.cupPrice;
    },
    hiredEmployee(){
      if(this.total >= this.employeeCost) {
        this.total -= this.employeeCost;
        this.employees++;
        this.employeeCost += 200;
      }
    },
    hiredManager(){
      if(this.total >= this.managerCost){
        this.total -= this.managerCost;
        this.managers++;
        this.managerCost += 1000;
      }
    },
    updateStats(){
      if(this.employees || this.managers) {
        this.total += this.employees;
        this.total += (this.managers * 5);
      }
    }
  },
  components: {
    appHeader,
    appFooter,
    appStatsKey,
    appStats,
    appOptionsKey,
    appOptions
  },
  mounted() {
    this.$root.$on('sold-cup', this.soldCup );
    this.$root.$on('hired-employee', this.hiredEmployee );
    this.$root.$on('hired-manager', this.hiredManager );

    /* Updating stats */
    setInterval(this.updateStats, 1000);
  }
}
</script>

<style>
  main {
    padding: 2em;
  }
  .items ul li div div, 
  .stats ul li div div {
    border-bottom: 1px solid lightgray;
    display: inline-block;
  }

  .items ul li div div {
    text-align: center;
    font-weight: bold;
  }

  .stats ul li div div {
    text-align: left;
  }
</style>