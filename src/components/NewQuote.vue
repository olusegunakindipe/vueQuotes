<template>
    <div class="row">
       <form>
           <div class="col-sm-8 col-sm-offset-2 col-xs-12 col-md-6 col-md-offset-3 form-group">
               <label for="Quote"> Quote</label>
               <textarea name="quote" id="quote" rows="5" class="form-control" v-model="quotes"></textarea>
           </div>
            <div class="col-sm-8 col-sm-offset-2 col-xs-12 col-md-6 col-md-offset-3 form-group">
                <button class="btn btn-primary" @click.prevent="createNew">Add Quote</button>
            </div>

       </form>
    </div>
</template>
<script>
export default {
    data(){
        return{
            quotes: ''
        }
    },
    methods:{
        createNew(){
            this.$emit('postQuote', this.quotes);
            this.quotes=''
        },

    }

}
</script>
<style>

</style>
