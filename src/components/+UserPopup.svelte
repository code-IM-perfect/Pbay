<script>
	import { authHandlers } from '../store/store';
</script>

<div
	class="popup absolute z-10 text-lg w-max h-max right-0 rounded-xl bg-neutral-800 border pointer-events-none"
>
	<ul class="p-4">
		<li class="p-3">
			<a href="/profile" class="pointer-events-auto">
				My Profile <i class="fa-solid fa-user mx-1"></i>
			</a>
		</li>
		<li class="p-3">
			<a href="/chat" class="pointer-events-auto">
				My Chats <i class="fa-solid fa-message mx-1"></i>
			</a>
		</li>
		<li class="p-3">
			<button class="pointer-events-auto" on:click={authHandlers.logout}>
				Log Out <i class="fa-solid fa-right-from-bracket mx-1"></i>
			</button>
		</li>
	</ul>
</div>

<style>
	.popup {
		background: rgba(100, 100, 100, 0.1);
		box-shadow: 0 0px 9px 0px rgba(120, 120, 120, 0.2);
		backdrop-filter: blur(5px);
		-webkit-backdrop-filter: blur(5px);
		border: 1px solid rgba(100, 100, 100, 0.15);
	}
</style>
