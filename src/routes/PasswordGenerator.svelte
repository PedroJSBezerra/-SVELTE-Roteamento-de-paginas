<script>
  import { onMount } from 'svelte';

  let password = ''
  let length = 8

  const generatePassword = () => {
    
    const charset = 'abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ0123456789';
    
    let retVal = "";
    
    for (let i = 0, n = charset.length; i < length; ++i) {
      retVal += charset.charAt(Math.floor(Math.random() * n));
    }
    
    password = retVal;
   
    return retVal;
  }

  let copy = (text) => {
    navigator.clipboard.writeText(text);
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
      <button on:click={() => copy(password)}>Copiar</button>
    {/if}
  </div>
</section>

