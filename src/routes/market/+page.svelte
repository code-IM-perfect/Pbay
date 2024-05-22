<script>
	import ProductMarket from '../../components/+ProductMarket.svelte';
</script>

<h1 class="text-center text-white font-medium text-5xl m-10 mt-20">Explore Products!</h1>

<section class="prodContainer grid gap-24 place-items-center">
	<ProductMarket />
	<ProductMarket name="This is a long 2 line name which can be handled" />
	<ProductMarket />
	<ProductMarket />
	<ProductMarket />
	<ProductMarket />
	<ProductMarket />
</section>

<style>
	.prodContainer {
		grid-template-columns: repeat(auto-fit, minmax(17rem, 1fr));
		margin: 10rem clamp(5rem, 10rem, 50vw);
	}
</style>
