<script>
  import Router from 'svelte-spa-router'
  import WhatsSemContato from './routes/WhatsSemContato.svelte'
  import Home from './routes/Home.svelte'
  import CalculadoraMulta from './routes/CalculadoraMulta.svelte'
  import Header from "./components/Header/Header.svelte"
  import QrCodeGenerator from "./routes/QrCodeGenerator.svelte"

  const routes = {
    '/': CalculadoraMulta,
    '/whatssemcontato': WhatsSemContato,
    '/calculadoramulta': CalculadoraMulta,
    '/qrcodegenerator': QrCodeGenerator,
  }
</script>

<Header/>
<main>
  <Router { routes }/>
</main>

<style>
</style>