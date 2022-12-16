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
    <div class="row">

      <div class="input">
        <label for="tamanho">
          <p><i class="bi bi-info"></i>Escolha o tamanho da senha em caracteres:</p>
        </label>
        <input id="tamanho" type="number" bind:value={length}>
        <button on:click={() => generatePassword()}>Gerar Senha</button>
      </div>

      <div class="output">
        <p>Sua senha gerada é:</p>
        {#if password != ''}
          <div class="result">
            <h3>{password}</h3>
            <button class="copy" on:click={() => copy(password)}>
              <i style="color:{copied?"green":""};" class="bi bi-clipboard{copied?"-check":""}"></i>
            </button>
          </div>
        {/if}    
      </div>
    
    </div>
  </div>
</section>

<style>
  .row {
    box-shadow: 2px 1px 8px #999;
    border-radius: 4px;
    padding: 10px;
  }

  .input {
  }

  .input button {
    font-size: 1.2rem;
  }

  #tamanho {
    width: 40px;
    font-size: 1.4rem;
  }

  .output {
  }

  .result {
    display: flex;
    justify-content: center;
    align-items: center;
  }

  button.copy {
    background: none;
    border: none;
    font-size: 2rem;
    padding: 0;
    margin: -1px;
    border: 1px dashed rgb(0 0 0 / 0%);
    margin-left: 10px;
  }

  button.copy:hover {
    border: 1px dashed blue;
    color: blue;
  }
</style>