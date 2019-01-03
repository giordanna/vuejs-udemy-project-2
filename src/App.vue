<template>
    <div class="container">
    	<app-header :quoteCount="quotes.length" :maxQuotes="maxQuotes"></app-header>
    	<app-quote-form @quoteAdded="addQuote($event)"></app-quote-form>
    	<app-quotes-list :quotes="quotes" @quoteDeleted="deleteQuote($event)"></app-quotes-list>
    	<app-footer></app-footer>
    </div>
</template>

<script>
	import Header from './components/Header.vue'
	import Footer from './components/Footer.vue'
	import QuotesList from './components/QuotesList.vue'
	import QuoteForm from './components/QuoteForm.vue'

    export default {
    	data: function() {
    		return {
    			quotes: [
    				'Just a Quote to see something'
    			],
    			maxQuotes: 10
    		}
    	},
        components: {
        	'app-header': Header,
        	'app-footer': Footer,
        	'app-quotes-list': QuotesList,
           	'app-quote-form': QuoteForm
        },
        methods: {
        	addQuote(quote) {
        		if (this.quotes.length >= this.maxQuotes) {
        			alert('Please delete Quotes first!')
        		}
        		else {
        			this.quotes.push(quote)
        		}
        	},
        	deleteQuote(index) {
        		this.quotes.splice(index, 1)
        	}
        }
    }
</script>

<style>
</style>
