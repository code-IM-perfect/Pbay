<script lang="ts">
	import type { User } from 'firebase/auth';
	import { authStore } from '../../store/store';
	import ProfileCard from '../../components/+ProfileCard.svelte';

	let userInfo = [
		{
			Label: 'Name',
			Value: 'DisplayName'
		},
		{
			Label: 'Email:',
			Value: 'Email'
		},
		{
			Label: 'PhoneNumber:',
			Value: '+91 xxx xxxx xxx'
		},
		{
			Label: 'RollNo:',
			Value: '123456'
		},
		{
			Label: 'Hall',
			Value: 'Hall 13'
		}
	];
	let currentUser: User | null;
	authStore.subscribe((val) => {
		currentUser = val.user;

		userInfo = [
			{
				Label: 'Name',
				Value: currentUser?.displayName as string
			},
			{
				Label: 'Email',
				Value: currentUser?.email as string
			},
			{
				Label: 'Phone Number',
				Value: currentUser?.phoneNumber as string
			},
			{
				Label: 'Roll No',
				Value: '123456'
			},
			{
				Label: 'Hall',
				Value: 'Hall 13'
			}
		];
	});

	let editing = false;
</script>

<section class="userInfo h-[90vh] grid place-items-center text-white text-center">
	<div class="infoPannel bg-neutral-700 rounded-2xl bg-opacity-10">
		<div class=" p-24 min-w-max w-[40vw] grid place-content-center">
			<div class="w-full grid place-content-center mb-10">
				<img src={currentUser?.photoURL} class=" rounded-2xl" alt="User ProfilePhoto" />
			</div>
			{#each userInfo as info}
				<div class="my-4">
					<h3 class=" text-base font-bold text-primary">{info.Label}</h3>
					{#if !editing}
						<p class="text-3xl">{info.Value}</p>
					{:else}
						<input type="text" placeholder={info.Value} />
					{/if}
				</div>
			{/each}
		</div>
	</div>
</section>

<section class=" mt-44">
	<h2 class="text-center text-5xl font-bold m-16">Items Bought</h2>
	<div class="cardContainer grid gap-24 place-items-center">
		<ProfileCard />
		<ProfileCard otherGuy="darthvader66" />
		<ProfileCard />
	</div>
</section>

<section class=" mt-44">
	<h2 class="text-center text-5xl font-bold m-16">Items Sold</h2>
	<div class="cardContainer grid gap-24 place-items-center">
		<ProfileCard otherGuy="Buyer" />
		<ProfileCard otherGuy="Buyer" />
		<ProfileCard otherGuy="Buyer" />
	</div>
</section>

<style>
	.cardContainer {
		grid-template-columns: repeat(auto-fit, minmax(17rem, 1fr));
		margin: 0 clamp(5rem, 10rem, 50vw) 10rem;
		grid-auto-rows: 1fr;
	}

	.userInfo {
		background-image: url(/src/lib/assets/sprinkle.svg);
	}
	.infoPannel {
		box-shadow: 0 0px 9px 0px rgba(100, 100, 100, 0.2);
		backdrop-filter: blur(8px);
		-webkit-backdrop-filter: blur(8px);
		border: 1px solid rgba(100, 100, 100, 0.15);
	}
</style>
