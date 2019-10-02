<template>
  <header>
    <md-toolbar class="md-primary">
        <span class="md-title">Lemonade Stand</span>
    </md-toolbar>
  </header>
</template>

<script>
export default {
    name: 'appHeader',
    data() {
        return {
            currentYear: new Date().getFullYear()
        }
    }
}
</script>