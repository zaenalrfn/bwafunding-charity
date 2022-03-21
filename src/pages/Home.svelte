<!-- bagian head -->
<!-- <svelte:head>
	<link rel="stylesheet" href="https://cdn.rawgit.com/kimeiga/bahunya/css/bahunya-0.1.3.css" />
</svelte:head> -->

<!-- bagian html -->

<Header />
<Welcome />
<CharityList />
<Promo />
<Footer />


<!-- bagian javascript -->
<script>

	import { onDestroy } from 'svelte';
	import {charities} from '../stores/data.js'
	import CharityList from '../components/CharityList.svelte';
	import Header from '../components/Header.svelte';
	import Welcome from '../components/Welcome.svelte';
	import Promo from '../components/Promo.svelte';
	import Footer from '../components/Footer.svelte';
	import Loader from '../components/Loader.svelte';

	onDestroy(function() {
		window.scrollTo(0, 0) // x, y
	})
</script>

