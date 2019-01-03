<template>
	<div class="row">
		<app-quote-detail
			v-for="(quote, index) in quotes"
			@click.native="deleteQuote(index)"
		>
			{{ quote }}
		</app-quote-detail>
	</div>
</template>

<script>
	import QuoteDetail from './QuoteDetail.vue'

	export default {
		props: ['quotes'],
		components: {
			'app-quote-detail': QuoteDetail
		},
		methods: {
			deleteQuote(index) {
				this.$emit('quoteDeleted', index)
			}
		}
	}
</script>

<style></style>