<template>
  <div id="app">
    <!-- appHeader -->
    <appHeader />

    <!-- main -->
    <main>
      <md-content class="md-elevation-1">
        <div class="md-layout md-gutter md-alignment-center-center">
          <app-stats-key />
          <app-stats />
          <app-options-key />
          <app-options />
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
  components: {
    appHeader,
    appFooter,
    appStatsKey,
    appStats,
    appOptionsKey,
    appOptions
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