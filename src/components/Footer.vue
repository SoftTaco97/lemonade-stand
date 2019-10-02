<template>
    <footer>
        <md-bottom-bar>
            <div class="md-layout-item md-size-95">
                <md-bottom-bar-item md-disabled>Martinez Designs</md-bottom-bar-item>
            </div>
            <div class="md-layout-item">
                <md-bottom-bar-item md-disabled>{{currentYear}}</md-bottom-bar-item>
            </div>
        </md-bottom-bar>
    </footer>
</template>

<script>
export default {
    name: 'appFooter',
    data() {
        return {
            currentYear: new Date().getFullYear()
        }
    }
}
</script>