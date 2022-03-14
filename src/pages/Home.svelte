<!-- bagian head -->
<!-- <svelte:head>
	<link rel="stylesheet" href="https://cdn.rawgit.com/kimeiga/bahunya/css/bahunya-0.1.3.css" />
</svelte:head> -->

<!-- bagian html -->



<!-- bagian javascript -->
<script>
	import CharityList from '../components/CharityList.svelte';
	import Header from '../components/Header.svelte';
	import Welcome from '../components/Welcome.svelte';
	import Promo from '../components/Promo.svelte';
	import Footer from '../components/Footer.svelte';
	import Loader from '../components/Loader.svelte';

	let title = "Charity";
	let data = getData();

	async function getData() {
		const res = await fetch('http://charity-api-bwa.herokuapp.com/charities');
		const data = await res.json();


		if(res.ok) {
			return data;
		} else {
			throw new Error(data);
		}
	}
	// let charities = ['Charity 1', 'Charity 2', 'Charity 3', 'Charity 4'];
</script>


<Header />
<Welcome />
{#await data}
	<Loader />
{:then charities}
	<CharityList {charities} />
{/await}
<Promo />
<Footer />