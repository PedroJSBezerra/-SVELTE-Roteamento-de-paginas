<script>

  let password = ''
  let length = 8

  let copied = false

  const generatePassword = () => {
    
    const charset = 'abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ0123456789';
    
    let retVal = ""
    
    for (let i = 0, n = charset.length; i < length; ++i) {
      retVal += charset.charAt(Math.floor(Math.random() * n))
    }
    
    password = retVal
    copied = false 
    return retVal
  }


  let copy = (text) => {
    navigator.clipboard.writeText(text)
    copied = true
  }

</script>

<section class="section">
  <div class="container">
    <label for="tamanho">
      <p>Escolha o tamanho da senha em caracteres:</p>
      <input id="tamanho" type="number" bind:value={length}>
    </label>
    <button on:click={() => generatePassword()}>Gerar Senha</button>
    <p>Sua senha gerada é:</p>
    {#if password != ''}
      <h3>{password}</h3>
      <button class="copy" on:click={() => copy(password)}>
        <i style="color:{copied?"green":""};" class="bi bi-clipboard{copied?"-check":""}"></i>
      </button>
    {/if}
  </div>
</section>

<style>
  .copy {
    border: none;
    background: none;
    font-size: 2rem;
  }

  .bi-clipboard:hover {
    color: blue;
  }
</style>