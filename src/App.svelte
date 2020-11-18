<script>
	import Header from './Header.svelte';
	import Preferences from './Components/Preferences.svelte';
	import CardRow from './Components/CardRow.svelte';
</script>

<main>
	<Header />

	<div class="contentRow">
		<h3>Høyest vurdert</h3>
		<CardRow studyCodes={['185481', '184887', '185880', '192504', '186134', '186605', '186807']} />
	</div>

	<div class="contentRow">
		<div class="recommendedHeader">
			<h3>Anbefalt for deg</h3>
			<Preferences />
		</div>
		
		<CardRow studyCodes={['186035', '186478', '186743', '184395', '185238', '185725', '185752']} />
	</div>
</main>

<style>
	h3 {
		text-transform: uppercase;
		font-size: 1.5em;
		font-weight: 100;
		margin-bottom: 0px;
	}

	.contentRow {
		margin-left: 10px;
	}

	.recommendedHeader {
		display: flex;
		flex-direction: row;
		justify-content: space-between;
		margin-top: 10px;
	}
</style>