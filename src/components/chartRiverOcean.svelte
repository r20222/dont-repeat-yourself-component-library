<script>
	import { onMount } from 'svelte';
	// import { Chart } from 'chart.js/auto';
	import SvgPlasticBottle from '/src/components/plastic-bottle-svg.svelte';

	export let data;

	// let chartInstance;
	// let oceanRiverData = data

</script>

<!-- * needs dynamic content -->
<!-- 1 = atom -->
<!-- 2 = molecule -->
<!-- 3 = organism -->

<h2>Plastic removed by ocean and river systems</h2><!-- * -->

<!-- show more info -->
<section>
	<input type="checkbox" id="my-checkbox">
	<label for="my-checkbox">Show more info</label>

	<div id="my-info" style="display: none;">
		<p>We named our company "The Ocean Cleanup" but a lot of plastic finds its way into the ocean via rivers first. To prevent the plastic from reaching the ocean, 
			we've put inceptors in the most polluting rivers. 
			<a href="/">Learn more</a>
		</p>
	</div>
</section>

<!-- 2x SVG bottle graph  -->
<div class="wrapper-graph-ocean-river">

	<section class="wrapper-ocean-trash-removed" >	<!-- style="--percentageBeforeAnimation:{percentage}" -->
		<a href="/ocean"><SvgPlasticBottle  /></a> 

		<div>
			<p>Ocean	<!-- {percentage} --> </p>

			<details class="more-info-ocean">
				<summary>More info</summary>
				The total amount of plastic removed by The Ocean Cleanup is..kg. The amount of plastic that is removed by the ocean system is ...kg. This means ..% of the total amount
				of collected trash comes from the ocean.
				<a href="/">go to ocean system</a>
			</details>
		</div>

	</section>

	<section class="wrapper-river-trash-removed">
		<a href="/river"><SvgPlasticBottle /></a>

		<div>
			<p>River</p> <!-- {percentage} -->
				
			<details class="more-info-river">
				<summary>More info</summary>
				The total amount of plastic removed by The Ocean Cleanup is..kg. <!-- * --> The amount of plastic removed by all river systems combined is ...kg. <!-- * --> This means ..% <!-- * --> of the
				total amount of collected trash comes from rivers.
			</details>
		</div>
	</section>

</div>


<style>

/* SVG styling */
.wrapper-graph-ocean-river {
		width: 100%;
		padding: 2em;
		display: flex; /* @media flex */
	}

	.wrapper-ocean-trash-removed {
		border: 1px solid lightblue;
	}

	.wrapper-river-trash-removed {
		border: 1px solid hotpink;
	}

	.wrapper-river-trash-removed, 
	.wrapper-ocean-trash-removed {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
		padding: 0 0 2rem 0;
	}

	/* Details styling */

	/* SVG animations */

	/* Container/media queries */

	/*  */


	
</style>
