<script>
  // Variable Farbe der Polygone anhand der Position (xi, yi) mit Modulo-Operator (Rest bei Division durch X)
  
	const elementWidth = 50;
	const elementCountX = 1000 / elementWidth;

	const elementHeight = 100;
	const elementCountY = 1000 / elementHeight;

	function getColor1(xi, yi) {
		if (yi % 2 == 0 && xi % 2 == 0) return '#0085ff'; // rosa
		else if (yi % 2 == 0 && xi % 2 == 1) return '#FF5A33'; // blau hell
		else if (yi % 2 == 1 && xi % 2 == 0) return '#FF5A33'; // blau hell
		else if (yi % 2 == 1 && xi % 2 == 1) return '#0085ff'; // rosa hell

    // if((xi + yi) % 2 == 0) return '#0085ff'; // rosa
    // else return '#FF5A33'; // blau hell

	}
</script>

<div class="svg-container">
	<svg class="svg-canvas" viewBox="0 0 1000 1000">
		{#each Array(elementCountY) as _, yi}
			{#each Array(elementCountX) as _, xi}
				<g transform="translate({xi * elementWidth} {yi * elementHeight})">
					<polygon points="0,{elementHeight / 2} {elementWidth / 2},0 {elementWidth},{elementHeight /
							2} {elementWidth / 2}, {elementHeight}" fill={getColor1(xi, yi)}></polygon>
				</g>
			{/each}
		{/each}
	</svg>
</div>
