<script>
  import Router from 'svelte-spa-router'
  import WhatsSemContato from './routes/WhatsSemContato.svelte'
  import Home from './routes/Home.svelte'
  import CalculadoraMulta from './routes/CalculadoraMulta.svelte'
  import Header from "./components/Header/Header.svelte"
  import QrCodeGenerator from "./routes/QrCodeGenerator.svelte"
  import PasswordGenerator from "./routes/PasswordGenerator.svelte"

  const routes = {
    '/': Home,
    '/whatssemcontato': WhatsSemContato,
    '/calculadoramulta': CalculadoraMulta,
    '/qrcodegenerator': QrCodeGenerator,
    '/passwordgenerator': PasswordGenerator,
  }
</script>

<Header/>
<main>
  <Router { routes }/>
</main>

<style>
</style>