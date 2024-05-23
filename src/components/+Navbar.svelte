<script lang="ts">
	import type { User } from 'firebase/auth';
	import { authStore } from '../store/store';
	import UserPopup from './+UserPopup.svelte';

	// const rand = (min: number, max: number) => Math.floor(Math.random() * (max - min)) + min;

	let links = [
		// { name: 'Home', url: '/' },
		{ name: 'Marketplace', url: '/market' },
		{ name: "Seller's Zone", url: '/seller' },
		{ name: 'Sign In', url: '/auth' }
	];

	let currentUser: User | null;
	authStore.subscribe((val) => {
		currentUser = val.user;
	});

	let userpopup = false;
</script>

<nav class="flex justify-between content-center items-center text-white mx-7">
	<h2 class="text-3xl font-extrabold p-4 mx-3">
		<a href="/" class="logo"
			><span id="p" class="logoChar">P</span><span id="b" class="logoChar">b</span><span
				id="a"
				class="logoChar">a</span
			><span id="y" class="logoChar">y</span></a
		>
	</h2>
	<ul class="flex justify-between">
		{#each links as link}
			<li class="navLink text-xl flex items-center inset-1">
				{#if link.name == 'Sign In' && currentUser}
					<button
						class="relative"
						on:click={() => {
							userpopup = !userpopup;
						}}
					>
						<img
							src={currentUser.photoURL}
							class="rounded-full h-8 w-8 m-4"
							alt="User's ProfilePhoto"
							class:imgGlow={userpopup}
						/>
						{#if userpopup}
							<UserPopup />
						{/if}
					</button>
				{:else}
					<a href={link.url} class="p-5">{link.name}</a>
				{/if}
			</li>
		{/each}
	</ul>
</nav>

<style>
	.imgGlow {
		box-shadow: 0 0px 9px 1px rgba(255, 255, 255, 0.5);
	}

	.logoChar {
		display: inline-block;
		animation-duration: 3.5s;
		animation-timing-function: ease-out;
		animation-iteration-count: 1;
	}

	#p {
		transform: translateX();
	}

	.logo:hover #p {
		animation-name: p;
	}
	.logo:hover #b {
		animation-name: b;
	}
	.logo:hover #a {
		animation-name: a;
	}
	.logo:hover #y {
		animation-name: y;
	}

	@keyframes p {
		0% {
			rotate: 0deg;
			animation-timing-function: cubic-bezier(0.19, 1, 0.22, 1);
		}
		13% {
			rotate: 380deg;
		}
		15% {
			translate: -300%;
			scale: 0.3;
			rotate: 380deg;
			animation-timing-function: cubic-bezier(0.95, 0.05, 0.795, 0.035);
		}
		20% {
			rotate: 360deg;
			animation-timing-function: cubic-bezier(0.95, 0.05, 0.795, 0.035);
		}
		30% {
			scale: 1;
			translate: -10%;
		}
		31% {
			scale: 0.6 1.4;
			translate: 40%;
		}
		35% {
			scale: 1.4 0.8;
			translate: -30%;
		}

		40% {
			scale: 0.8 1.2;
			translate: 20%;
		}
		45% {
			scale: 1.1 0.9;
			translate: -20%;
		}
		/* 50% {
			scale: 0.9 1.1;
			translate: 20%;
		} */
		50% {
			scale: 1;
			translate: 0;
		}
		100% {
			rotate: calc(360deg);
		}
	}
	@keyframes b {
		0% {
			rotate: 0deg;
			animation-timing-function: cubic-bezier(0.19, 1, 0.22, 1);
		}
		13% {
			rotate: 380deg;
		}
		15% {
			translate: -150%;
			scale: 0.3;
			rotate: 380deg;
			animation-timing-function: cubic-bezier(0.95, 0.05, 0.795, 0.035);
		}
		20% {
			rotate: 360deg;
			animation-timing-function: cubic-bezier(0.95, 0.05, 0.795, 0.035);
		}
		30% {
			scale: 1;
			translate: -10%;
		}
		31% {
			scale: 0.7 1.3;
			translate: 40%;
		}
		35% {
			scale: 1.3 0.9;
			translate: -30%;
		}

		40% {
			scale: 0.9 1.1;
			translate: 20%;
		}
		45% {
			scale: 1.05 0.95;
			translate: -20%;
		}
		/* 50% {
			scale: 0.9 1.1;
			translate: 20%;
		} */
		50% {
			scale: 1;
			translate: 0;
		}
		100% {
			rotate: calc(360deg);
		}
	}
	@keyframes y {
		0% {
			rotate: 0deg;
			animation-timing-function: cubic-bezier(0.19, 1, 0.22, 1);
		}
		13% {
			rotate: 380deg;
		}
		15% {
			translate: 300%;
			scale: 0.3;
			rotate: 380deg;
			animation-timing-function: cubic-bezier(0.95, 0.05, 0.795, 0.035);
		}
		20% {
			rotate: 360deg;
			animation-timing-function: cubic-bezier(0.95, 0.05, 0.795, 0.035);
		}
		30% {
			scale: 1;
			translate: 10%;
		}
		31% {
			scale: 0.6 1.4;
			translate: -40%;
		}
		35% {
			scale: 1.4 0.8;
			translate: 30%;
		}

		40% {
			scale: 0.8 1.2;
			translate: -20%;
		}
		45% {
			scale: 1.1 0.9;
			translate: 20%;
		}
		/* 50% {
			scale: 0.9 1.1;
			translate: 20%;
		} */
		50% {
			scale: 1;
			translate: 0;
		}
		100% {
			rotate: calc(360deg);
		}
	}
	@keyframes a {
		0% {
			rotate: 0deg;
			animation-timing-function: cubic-bezier(0.19, 1, 0.22, 1);
		}
		13% {
			rotate: 380deg;
		}
		15% {
			translate: 150%;
			scale: 0.3;
			rotate: 380deg;
			animation-timing-function: cubic-bezier(0.95, 0.05, 0.795, 0.035);
		}
		20% {
			rotate: 360deg;
			animation-timing-function: cubic-bezier(0.95, 0.05, 0.795, 0.035);
		}
		30% {
			scale: 1;
			translate: 10%;
		}
		31% {
			scale: 0.7 1.3;
			translate: -20%;
		}
		35% {
			scale: 1.3 0.9;
			translate: 15%;
		}

		40% {
			scale: 0.9 1.1;
			translate: -10%;
		}
		45% {
			scale: 1.05 0.95;
			translate: 10%;
		}
		/* 50% {
			scale: 0.9 1.1;
			translate: 20%;
		} */
		50% {
			scale: 1;
			translate: 0;
		}
		100% {
			rotate: calc(360deg);
		}
	}
</style>
