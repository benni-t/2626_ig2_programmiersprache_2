<script>

	// Selber machen lassen, nun können Sie Positionen über Funktionen und Modulo-Operatoren berechnen, um komplexere Muster zu erstellen.
	const elementWidth = 50;
	const elementCountX = 1000 / elementWidth;

	const elementHeight = 100;
	const elementCountY = (1000 / elementHeight) * 2;

	function getColor1(xi, yi) {
		if (yi % 2 == 0 && xi % 2 == 0) return 'red'; 
		if (yi % 2 == 0 && xi % 2 == 1) return 'blue';
		if (yi % 2 == 1 && xi % 2 == 0) return 'yellow'; 
		if (yi % 2 == 1 && xi % 2 == 1) return 'green'; 
	}

	function calculatePosition(xi, yi) {
		if (yi % 2 == 0) {
			let x = xi * elementWidth;
			let y = yi * (elementHeight / 2);
			return `translate(${x} ${y})`;
		} else {
			let x = xi * elementWidth - elementWidth / 2;
			let y = yi * (elementHeight / 2);
			return `translate(${x} ${y})`;
		}
	}
</script>

<div class="svg-container">
	<svg class="svg-canvas" viewBox="0 0 1000 1000">
		{#each Array(elementCountY) as _, yi}
			{#each Array(elementCountX) as _, xi}
				<g transform={calculatePosition(xi, yi)}>
					<polygon points="0,{elementHeight / 2} {elementWidth / 2},0 {elementWidth},{elementHeight /
							2} {elementWidth / 2}, {elementHeight}" fill={getColor1(xi, yi)}></polygon>
				</g>
			{/each}
		{/each}
	</svg>
</div>
