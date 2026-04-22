<script>
	// Zusätzliche variable Größe der Elemente anhand der Width und Height vom Element

	const elementWidth = 50;
	const elementCountX = 1000 / elementWidth;

	const elementHeight = 100;
	const elementCountY = 1000 / elementHeight;
</script>

<div class="svg-container">
	<svg class="svg-canvas" viewBox="0 0 1000 1000">
		{#each Array(elementCountY) as _, yi}
			{#each Array(elementCountX) as _, xi}
				<g transform="translate({xi * elementWidth} {yi * elementHeight})">
					<polygon
						points="0,{elementHeight / 2} {elementWidth / 2},0 {elementWidth},{elementHeight /
							2} {elementWidth / 2}, {elementHeight}"
						fill="#0085ff"
					></polygon>
				</g>
			{/each}
		{/each}
	</svg>
</div>
