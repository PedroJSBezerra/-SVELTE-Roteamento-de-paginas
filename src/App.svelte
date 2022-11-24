<script>
  import Router from 'svelte-spa-router'
  import WhatsSemContato from './routes/WhatsSemContato.svelte'
  import Home from './routes/Home.svelte'
  import CalculadoraMulta from './routes/CalculadoraMulta.svelte'
  import Header from "./components/Header/Header.svelte"

  const routes = {
    '/': Home,
    '/whatssemcontato': WhatsSemContato,
    '/calculadoramulta': CalculadoraMulta
  }
</script>

<Header/>
<main>
  <Router { routes }/>
</main>

<style>
</style>