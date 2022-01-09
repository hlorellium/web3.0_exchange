<script lang="ts">
	import Footer from '$lib/Footer.svelte';
	import Header from '$lib/header/Header.svelte';
	import Services from '$lib/Services.svelte';
	import Transactions from '$lib/Transactions.svelte';
	import Welcome from '$lib/Welcome.svelte';
</script>

<div class="gradient-bg-welcome">
	<Header />
	<Welcome />
</div>

<Services />
<Transactions />
<Footer />
