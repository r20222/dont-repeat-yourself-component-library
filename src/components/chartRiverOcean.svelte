<script>
	import { onMount } from 'svelte';
	import { Chart } from 'chart.js/auto';
	import SvgPlasticBottle from '/src/components/plastic-bottle-svg.svelte';

	export let data;

	// let chartInstance;
	// let oceanRiverData = data
</script>

<h2>Plastic removed by ocean and river systems</h2>

<!-- show more info -->
<button>Show more info</button>
<p class="additional-info-ocean-river-systems">Additional ocean and river information: it's called The Ocean Cleanup 
	but a lot of plastic finds its way into the ocean via rivers first. To prevent the plastic from reaching the ocean, 
	we put inceptors in the most polluting rivers.</p>

<!-- 2x SVG bottle graph  -->
<div class="wrapper-svg-ocean-and-river">

	<div class="wrapper-ocean-trash-removed">
		<a href="/ocean"><SvgPlasticBottle  /></a> 
		<div>
			<p>Ocean</p>
			<button>Show more info</button><!-- this needs to be hidden and shown when click/hover on i -->
			<p class="add-info-ocean-systems">
				The total amount of plastic removed by The Ocean Cleanup is..kg. The amount of plastic that is removed by the ocean system is ...kg. This means ..% of the total amount
				of collected trash comes from the ocean.
			</p>
		</div>
	</div>

	<div class="wrapper-river-trash-removed">
		<a href="/river"><SvgPlasticBottle /></a>
		<div>
			<p>River</p>
			<button>Show more info</button><!-- this needs to be hidden and shown when click/hover on i -->
			<p class="add-info-river-systems">
				The total amount of plastic removed by The Ocean Cleanup is..kg. The amount of plastic removed by all river systems combined is ...kg. This means ..% of the
				total amount of collected trash comes from rivers.
			</p>
		</div>
	</div>

</div>

<style>

/* SVG styling */
.wrapper-svg-ocean-and-river {
		background-color: green;
		padding: 2em;
		display: flex;
	}

	.wrapper-ocean-trash-removed {
		background-color: lightblue;
	}

	.wrapper-river-trash-removed {
		background-color: red;
	}

	/* SVG animations */

	
</style>
