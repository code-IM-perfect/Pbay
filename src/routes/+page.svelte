<script>
	import GlowInfoBox from '../components/+GlowInfoBox.svelte';

	// const randomBox = () => {
	// 	return '<WhyBoxes size="2.1" t="" l="" rot="-23.7" color="bg-red-300" txt="What?" />';
	// };
</script>

<section
	class="flex justify-center items-center text-white h-[80vh] bg-no-repeat bg-center"
	style="background-image: url(/src/lib/assets/heroBackk.svg);"
>
	<h1 class="text-center text-8xl font-bold leading-[1.2]">
		Everything You Need<br /><span class=" text-primary">Within Campus!</span>
	</h1>
</section>

<section class="text-dark flex justify-center content-center mt-[30vh]">
	<div class="w-full mx-[20vw] my-[20vh] min-h-[50vh] relative">
		<div class="glassInfobox relative rounded-2xl h-full grid place-content-center">
			<div class="p-14 px-20 grid place-content-center">
				<h2 class="text-center text-4xl font-bold my-5">What is CampusBazaar?</h2>
				<p class="text-center max-w-[40vw] text-lg">
					CampusBazaar is an intiative by pclub iitk to make the process of buying and selling stuff
					within campus as easy as possible, by making a dedicated platform for it. Sellers can
					reach a large audience and buyers get a huge range of products.<br />With this initiative,
					we aim to reduce wasteage and support a sustainable future.
				</p>
				<button class="mt-[4vw]">Get Started Now!</button>
			</div>
		</div>
	</div>
</section>

<section>
	<!-- <GlowInfoBox /> -->
</section>

<style>
	.glassInfobox {
		background: rgba(255, 255, 255, 0.6);
		box-shadow: 0 8px 32px 0 rgba(200, 200, 200, 0.5);
		backdrop-filter: blur(8.5px);
		-webkit-backdrop-filter: blur(8.5px);
	}
</style>
