<script>
	// EACH-Block: Berechnung der Position der Elemente über xi und yi, fixe Größe der Elemente.

	console.log(Array(10));
</script>

<div class="svg-container">
	<svg class="svg-canvas" viewBox="0 0 1000 1000">
		{#each Array(10) as _, yi}
			{#each Array(10) as _, xi}
				<g transform="translate({xi * 100} {yi * 100})">
					<polygon points="0,50 50,0 100,50 50, 100" fill="#FF5A33"></polygon>
				</g>
			{/each}
		{/each}
	</svg>
</div>
