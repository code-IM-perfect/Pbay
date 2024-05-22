<script lang="ts">
	const rand = (min: number, max: number) => Math.floor(Math.random() * (max - min)) + min;

	let links = [
		// { name: 'Home', url: '/' },
		{ name: 'Marketplace', url: '/market' },
		{ name: "Seller's Zone", url: '/sell' },
		// { name: 'Sign Up', url: '#' },
		{ name: 'Sign In', url: '#' }
	];
</script>

<nav class="flex justify-between content-center items-center text-white">
	<h2 class="text-3xl font-extrabold p-4 mx-3"><a href="/">CampusBazaar</a></h2>
	<ul class="flex justify-between mx-5">
		{#each links as link}
			<li class="navLink text-xl flex items-center inset-1">
				<a href={link.url} class="p-5">{link.name} </a>
			</li>
		{/each}
	</ul>
</nav>
