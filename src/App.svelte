<script>
  import Home from './pages/Home.svelte';
  import Router from 'svelte-spa-router'
  import Add from './pages/Add.svelte';
  import Edit from './pages/Edit.svelte';

  const routes = {
    '/': Home,
    '/add': Add,
    '/edit/:id': Edit,
    '*': Home
  };
</script>

<main>
	<Router routes={routes}></Router>
</main>

<style>
	main {
		background-color: rgb(255, 251, 246);
		padding: 2em;
		height: 100%;
		overflow-y: scroll;
	}
</style>