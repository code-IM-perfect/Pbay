<script>
	import '../app.css';
	import Navbar from '../components/+Navbar.svelte';
	import Footer from '../components/+Footer.svelte';
	import { onMount } from 'svelte';
	import { auth } from '$lib/firebase';
	import { authStore } from '../store/store';

	onMount(() => {
		const unsubscribe = auth.onAuthStateChanged(async (user) => {
			if (!user) {
				authStore.update(() => {
					return {
						user: null
					};
				});
			} else {
				authStore.update(() => {
					return {
						user: user
					};
				});
			}
		});
		return unsubscribe;
	});
</script>

<div>
	<Navbar />
	<slot />
	<Footer />
</div>
