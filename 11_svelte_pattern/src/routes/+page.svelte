<script>
  import Header from '$lib/components/Header.svelte'
  import PatternNavigation from '$lib/components/PatternNavigation.svelte'
  import Pattern from '$lib/components/Pattern1_3.svelte'
  import Footer from '$lib/components/Footer.svelte'
</script>

<div class="app-container">
  <Header />

	<main class="app-main">
    <PatternNavigation />
    <Pattern />
	</main>

  <Footer />
</div>