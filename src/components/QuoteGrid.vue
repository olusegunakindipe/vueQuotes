<template>
    <div class="row">
        <app-quote v-for="(quote, index) in quotes" @click.native="deleteQuote(index)">
            {{quote}}
        </app-quote>
    </div>
</template>
<script>
import Quote from './Quote.vue';
export default {
    props : ['quotes'],
    mwthods : {
        deleteQuote(index){
        this.$emit('QuoteDeleted', index);
        }
    },
    components:{
        'app-quote': Quote
    }
}
</script>
<style>

</style>
