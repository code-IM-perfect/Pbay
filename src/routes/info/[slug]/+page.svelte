<div class="text-white grid mainCont m-32 place-content-center">
	<div class="img m-9 rounded-xl bg-cover bg-center bg-no-repeat"></div>
	<div class="grid content-center">
		<h1 class="text-5xl text-primary">Product Name</h1>
		<div class="price flex m-1">
			<h2 class="text-4xl font-bold">₹Price</h2>
			<p class="mx-2 my-1 text-sm">Suggested by Seller</p>
		</div>
		<p class=" mt-3 mx-1">Age: X years</p>
		<p class=" mt-1 mx-1">Seller: Neofetch</p>
		<a
			class="locate mx-1 underline decoration-primary"
			href="https://maps.app.goo.gl/vzCie4Tx6o9TpK6F7"
			target="_blank">Locate Seller</a
		>
		<div class="flex">
			<a
				class="startChat font-semibold hover:bg-primary hover:text-dark text-xl m-6 mx-1 p-3 border-2 border-primary"
				href="/chat">Start Chat</a
			>
		</div>
	</div>
</div>

<style>
	.mainCont {
		grid-template-columns: minmax(40vh, 65vh) minmax(max-content, 1fr);
	}
	.img {
		height: 55vh;
		max-width: 65vh;
		background-image: url(/static/assets/placeholder/1.jpg);
	}
	.price p {
		align-self: flex-end;
	}
	.locate {
		width: max-content;
		transition: all 0.4s;
	}
	.locate:hover {
		text-underline-offset: 0.15em;
	}
	.startChat {
		transition: all 0.2s cubic-bezier(0.25, 0.46, 0.45, 0.94);
	}
	.startChat:hover {
		border-radius: 0.5em;
		box-shadow: 0px 0px 15px 5px rgba(76, 255, 180, 0.5);
		transform: scale(1.2);
	}
</style>
