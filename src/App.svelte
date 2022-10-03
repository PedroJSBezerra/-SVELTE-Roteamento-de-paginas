<script>
  import Router from 'svelte-spa-router'
  import WhatsSemContato from './routes/WhatsSemContato.svelte'
  import Home from './routes/Home.svelte'
  import CalculadoraMulta from './routes/CalculadoraMulta.svelte'
  import NavOffCanvas from './components/NavOffCanvas.svelte'

  const routes = {
    '/': Home,
    '/whatssemcontato': WhatsSemContato,
    '/calculadoramulta': CalculadoraMulta
  }
</script>

<NavOffCanvas />
<Router { routes }/>