<script>
  import Home from './pages/Home.svelte';
  import Router from 'svelte-spa-router'
  import Add from './pages/Add.svelte';
  import Edit from './pages/Edit.svelte';
  import TopAppBar from './components/TopAppBar.svelte';

  const routes = {
    '/': Home,
    '/add': Add,
    '/edit/:id': Edit,
    '*': Home
  };

  let prominent = false;
  let dense = false;
  let secondaryColor = false;
</script>

<main>
  <div class="top-app-bar-container flexor">
    <Router routes={routes}></Router>
  </div>
</main>

<style>

  .top-app-bar-container {
    height: 100%;
    width: 100%;
    position: fixed;
  }
  .top-app-bar-container {
    overflow: auto;
    display: inline-block;
  }
  .flexor {
    display: inline-flex;
    flex-direction: column;
  }
</style>