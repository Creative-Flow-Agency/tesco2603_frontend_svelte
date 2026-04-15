<script>
  import Router from 'svelte-spa-router';
  import Home from './pages/Home.svelte';
  import Nyertesek from './pages/Nyertesek.svelte';
  import Szabalyzat from './pages/Szabalyzat copy.svelte';
  import GyakoriKerdesek from './pages/GyakoriKerdesek.svelte';

  const routes = {
    '/nyertesek': Nyertesek,
    '/szabalyzat': Szabalyzat,
    '/faq': GyakoriKerdesek,
    '/': Home,
  };
</script>

<main>
  <Router {routes} />
</main>
