<script lang="ts">
	import { onMount } from 'svelte';

	onMount(async () => {
		//npm install --save-dev @types/plotly.js-dist-min
		//npm i plotly.js-dist-min
		const { newPlot } = await import('plotly.js-dist-min');

		const trace1: Plotly.Data = {
			x: [1, 2, 3, 4],
			y: [10, 15, 13, 17],
			type: 'scatter'
		};

		const trace2: Plotly.Data = {
			x: [1, 2, 3, 4],
			y: [16, 5, 11, 9],
			type: 'scatter'
		};

		const data: Plotly.Data[] = [trace1, trace2];

		newPlot('myDiv', data, undefined, { scrollZoom: true });
	});
</script>

<div id="myDiv" />
