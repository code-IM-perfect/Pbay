<script>
	export let img = '/src/lib/assets/placeholder/1.jpg';
	export let name = 'Product Name';
	export let price = 'Price';
	export let seller = 'Seller';
	export let time = 'Time';

	// let glowBlur = 12;
	// let glowRange = 8;
	// let glowOpacity = 0.5;
</script>

<div
	class="cardContainer hover:bg-white hover:text-dark rounded-xl grid text-white h-full min-h-96 w-full max-w-96"
	style=""
>
	<div
		class="image rounded-xl m-4 h-72 bg-center bg-no-repeat bg-cover"
		style="background-image:url({img}); align-self:normal;"
	></div>
	<h4 class="text-xl font-medium mx-6 my-3">{name}</h4>
	<h3 class="text-4xl font-bold mx-6">₹{price}</h3>
	<div class="lastRow flex justify-between mx-6 my-6">
		<p>{seller}</p>
		<p class="justify-self-end">{time}</p>
	</div>
</div>

<style>
	.cardContainer {
		/* grid-template-rows: 12fr auto auto 1fr; */
		/* grid-template-rows: subgrid; */
		align-items: center;
		/* grid-row: 1/5; */
		/* background-color: #111; */
		box-shadow: 0px 0px 14px 10px rgba(0, 0, 0, 0.6);
		transition: all 0.3s cubic-bezier(0.25, 0.46, 0.45, 0.94);
	}

	.cardContainer:hover {
		box-shadow: 0px 0px 40px 15px rgba(255, 255, 255, 0.5);
		transform: scale(1.1);
	}

	h3 {
		align-self: baseline;
	}
</style>
