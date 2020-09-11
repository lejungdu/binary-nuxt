<template>
    <div v-if="data.nodes && data.nodes.length && depth < 5">
        <v-btn @click="$emit('children-display')" small>{{buttonDisplay}}</v-btn>
    </div>
</template>

<script>
/* eslint-disable */ 
export default {
    name: 'BranchButton',
    props: ['data', 'depth', 'showChildren'],
    computed: {
        buttonDisplay: function(){ return this.showChildren ? 'CLOSE' : 'OPEN' },
    },
}
</script>