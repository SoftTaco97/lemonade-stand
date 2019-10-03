<template>
    <div class="md-layout-item md-size-10">
        <md-list>
            <md-list-item>
                <md-button class="md-raised" @click="sellACup">
                    + {{ cupPrice }} $
                </md-button>
            </md-list-item>
            <md-list-item>
                <md-button class="md-raised md-primary" @click="hireEmployee">
                    - {{ employeeCost }} $
                </md-button>
            </md-list-item>
            <md-list-item>
                <md-button class="md-raised md-accent" @click="hireManager">
                    - {{ managerCost }} $
                </md-button>
            </md-list-item>
        </md-list>
    </div>
</template>

<script>
export default {
    name: 'Options',
    props: {
        cupPrice: {
            type: Number,
            required: true
        },
        employeeCost: {
            type: Number,
            required: true
        },
        managerCost: {
            type: Number,
            required: true
        }
    },
    methods: {
        sellACup() {
            this.$root.$emit('sold-cup', true);
        },
        hireEmployee(){
            this.$root.$emit('hired-employee', true);
        },
        hireManager(){
            this.$root.$emit('hired-manager', true);
        }
    }
}
</script>