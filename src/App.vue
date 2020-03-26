<template>
    <div class="container">
        <app-header :quoteCount="quotes.length" :maxQuotes="maxQuotes"></app-header>
        <app-new-quote @postQuote="newQuote"></app-new-quote>
       <app-quote-grid :quotes="quotes" @QuoteDeleted="deleteQuote(index)"></app-quote-grid>
       <div class="row">
           col-sm-12 <text-center>
               <div class="alert alert-info">Info: Click on a Quote to delete</div>
           </text-center>
       </div>
    </div>
</template>

<script>
import Header from './components/Header.vue';
import QuoteGrid from './components/QuoteGrid.vue';
import NewQuote from './components/NewQuote.vue';
export default {
    
    data(){
        return{
            quotes:[
                'This is a wonderful and amazing quote'
            ],
            maxQuotes : 10,
        }
    },
    methods:{
        newQuote(quote)
        { 
            if(this.quotes.length >= this.maxQuotes){
               return alert('delete a post to add new one');
            }
            this.quotes.push(quote);
        },
        deleteQuote(index)
        {
            this.quotes.splice(index, 1);
        }
    },
    components: {
        'app-quote-grid' : QuoteGrid,
        'app-new-quote': NewQuote,
        'app-header' : Header,

    }
}
</script>

<style>
  
</style>
