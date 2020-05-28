<script>
	let MHR = 180;
	let RHR = 50;
	let percent = 65;
	let zoneResult = 0;

	$: {
		zoneResult = ((MHR - RHR) * (percent/100)) + RHR;
		zoneResult = zoneResult.toFixed(1);
	}
</script>

<main>
	<h1>Heart rate zones!</h1>

	<section>
		<div>
			<label for="mhr">Max Heart Rate</label>
			<input name="mhr" type="number" bind:value={MHR} />
		</div>
		<div>
			<label for="rhr">Resting Heart Rate</label>
			<input name="rhr" type="number" bind:value={RHR} />
		</div>
		<div>
			<label for="percent">Percentage</label>
			<input name="percent" type="number" bind:value={percent} />
		</div>
	</section>

	<p>Your heartrate for {percent}% is {zoneResult}</p>
</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	h1 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>