<script lang="ts">
	import { authHandlers } from '../../store/store';
</script>

<div class="grid place-items-center h-[80vh]">
	<div>
		<h1 class="text-center text-3xl">Login</h1>
		<button
			class="m-4 p-3 border-2 border-primary text-primary"
			on:click={() => authHandlers.loginWithGoogle('/market')}
		>
			<i class="fa-brands fa-google mx-1" />
			Sign In with Google
		</button>
	</div>
</div>

<style>
	button {
		transition: all 0.2s cubic-bezier(0.25, 0.46, 0.45, 0.94);
	}
	button:hover {
		border-radius: 0.5em;
		box-shadow: 0px 0px 15px 5px rgba(76, 255, 180, 0.5);
		transform: scale(1.2);
	}
</style>
