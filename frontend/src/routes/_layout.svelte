<script>
	import Nav from '../components/Nav.svelte'
	import Footer from '../components/Footer.svelte'

	export let segment;
</script>

<style>
</style>

<Nav {segment}/>

<main>
	<!-- deixa o footer no fim da página estendendo o conteúdo -->
	<!-- e dá espaçamento dos lados e de cima  -->
	<div class="wrapper d-flex flex-column min-vh-100 px-5 mt-3">
		<slot></slot>
	</div>
</main>

<Footer/>
