<template>
    <div class="row">
        <div class="col-sm-8-col-sm-offset-2 col-xs-12 col-md-6 col-md-offset-3 form-group">
            <form>
                <label>Quote</label>
                <textarea row="3" class="form-control" v-model="quote"></textarea>
            </form>
        </div>
        <div class="col-sm-8-col-sm-offset-2 col-xs-12 col-md-6 col-md-offset-3 form-group">
            <button class="btn btn-primary" @click.prevent="createNew">Add Quote</button>
        </div>
    </div>
</template>

<script>
    export default {
        data: function() {
            return {
                quote: ''
            }
        },
        methods: {
            createNew() {
               this.$emit('quoteCreated', this.quote);
               this.quote = '';
            }
        }
    }
</script>

<style>
    
</style>