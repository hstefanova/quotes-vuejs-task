<template>
    <div class="row">
        <Quote 
            v-for="(quote, index) in quotes"
            @click.native="deleteQuote(index)"
            >
            <p>{{ quote }}</p>
        </Quote>
    </div>
</template>

<script>
    import Quote from './Quote.vue'

    export default {
        props: ['quotes'],
        components: {
            Quote: Quote
        },
        methods: {
            deleteQuote(index) {
              this.$emit('quoteDeleted', index)  
            }
        }
    }
</script>

<style>
    .panel-body { 
        font-family: 'Arizonia', cursive;
        font-size: 24px;
        color: #6e6e6e;
    }

    .quote {
        cursor: pointer;
        transition: background .2s;
    }

    .quote:hover {
        background-color: #ffe2e2;
    }
</style>