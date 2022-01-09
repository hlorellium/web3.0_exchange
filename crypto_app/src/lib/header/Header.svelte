<script lang="ts">
	import { fly } from 'svelte/transition';

	import logo from './logo.png';
	import NavItem from './NavItem.svelte';

	let menuIsToggled = false;
</script>

<header
	class="container mx-auto md:mx-auto flex md:justify-center justify-between p-4 items-center"
>
	<div class="md:flex-[0.5] flex-initial justify-center items-center">
		<img src={logo} alt="krypt" class="w-32 cursor-pointer" />
	</div>

	<ul
		class="text-white md:flex hidden list-none flex-row justify-between items-center flex-initial"
	>
		{#each ['Market', 'Exchange', 'Tutorials', 'Wallets'] as item}
			<NavItem title={item} />
		{/each}
		<NavItem
			title="Login"
			classProps="bg-blue-600 py-2 px-7 mx-4 rounded-full cursor-pointer hover:bg-blue-700"
		/>
	</ul>

	<ul class="flex md:hidden relative">
		{#if menuIsToggled}
			<ul
				class="z-10 fixed -top-0 -right-2 p-3 w-[70vw] h-screen shadow-2xl md:hidden list-none
        flex flex-col justify-start items-end rounded-md blue-glassmorphism text-white animate-slide-in"
				transition:fly={{ x: 300 }}
			>
				<li class="text-xl w-full my-2">
					<svg
						xmlns="http://www.w3.org/2000/svg"
						class="h-6 w-6"
						fill="none"
						viewBox="0 0 24 24"
						stroke="currentColor"
						on:click={() => (menuIsToggled = false)}
					>
						<path
							stroke-linecap="round"
							stroke-linejoin="round"
							stroke-width="2"
							d="M6 18L18 6M6 6l12 12"
							color="white"
						/>
					</svg>
				</li>

				{#each ['Market', 'Exchange', 'Tutorials', 'Wallets'] as item}
					<NavItem title={item} classProps="my-2 text-lg" />
				{/each}
			</ul>
		{:else}
			<svg
				xmlns="http://www.w3.org/2000/svg"
				class="h-6 w-6"
				fill="#fff"
				viewBox="0 0 24 24"
				stroke="currentColor"
				on:click={() => (menuIsToggled = true)}
			>
				<path
					stroke-linecap="round"
					stroke-linejoin="round"
					stroke-width="2"
					d="M4 8h16M4 16h16"
					color="white"
				/>
			</svg>
		{/if}
	</ul>
</header>
