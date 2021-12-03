<template>
    <v-data-table :headers="headers" :items="items" hide-default-footer>
        <template v-slot:item.duration="{item}">
            {{item.duration|formatoHHmm}}
        </template>
    </v-data-table>
</template>

<script>
    export default {
        props: {
            items: {
                type: Array,
                default: () => [] 
            },
            headers: {
                type:Array,
                default: () => []
            }
        },
        
        filters: {
            formatoHHmm: (value) => {
                return value.split(':')[0] + 'h ' + value.split(':')[1] + 's'
            } 
        }
    }
</script>

<style scoped>

</style>