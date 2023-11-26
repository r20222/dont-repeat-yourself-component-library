<script>
	import { onMount } from 'svelte';
	// import { Chart } from 'chart.js/auto';
	import SvgPlasticBottle from '/src/components/plastic-bottle-svg.svelte';

	export let data;

	// let chartInstance;
	// let oceanRiverData = data

// 	document.querySelector("#my-checkbox").addEventListener("click", function() {
//   const info = document.querySelector("#my-info");
//   info.style.display = info.style.display === "none" ? "block" : "none";
// });

// document.querySelector("#my-checkbox").addEventListener("click", function() {
//   const info = document.querySelector("#my-info");
//   info.style.display = "block";
// });
</script>

<h2>Plastic removed by ocean and river systems</h2>

<!-- show more info -->
<section>
	<input type="checkbox" id="my-checkbox">
	<label for="my-checkbox">Show more info</label>

	<div id="my-info" style="display: none;">
		<p>Additional ocean and river information: it's called The Ocean Cleanup 
			but a lot of plastic finds its way into the ocean via rivers first. To prevent the plastic from reaching the ocean, 
			we've put inceptors in the most polluting rivers.	</p>
	</div>
</section>


<!-- 2x SVG bottle graph  -->
<div class="wrapper-graph-ocean-river">

	<section class="wrapper-ocean-trash-removed" >	<!-- style="--percentageVoorAnimatie:{percentage}" -->
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
				The total amount of plastic removed by The Ocean Cleanup is..kg. The amount of plastic removed by all river systems combined is ...kg. This means ..% of the
				total amount of collected trash comes from rivers.
			</details>
		</div>
	</section>

</div>

<label class="switch">
	<input type="checkbox">
	<span class="slider round"></span>
  </label>
  <span>Show more info</span>
  <div id="my-info" style="display: none;">
	<p>The total amount of plastic removed by The Ocean Cleanup is..kg. The amount of plastic removed by all river systems combined is ...kg. This means ..% of the
		total amount of collected trash comes from rivers.</p>
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

	/* SVG animations */

	
</style>
