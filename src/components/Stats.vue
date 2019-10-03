<template>
  <div class="md-layout-item md-size-25 stats">
    <md-list>
        <md-list-item>
            {{ total }} $
        </md-list-item>
        <md-list-item>
            {{ employees }}
        </md-list-item>
        <md-list-item>
            {{ managers }}
        </md-list-item>
    </md-list>
    </div>
</template>

<script>
export default {
    name: 'stats',
    props: {
        total: {
            type: Number, 
            required: true
        },
        employees: {
            type: Number,
            required: true
        },
        managers: {
            type: Number,
            required: true
        }
    }
}
</script>