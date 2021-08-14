<script>
	import Nav from '../components/Nav.svelte';

	export let segment;
</script>



<Nav/>

<main class="form-signin">
	<slot></slot>
</main>