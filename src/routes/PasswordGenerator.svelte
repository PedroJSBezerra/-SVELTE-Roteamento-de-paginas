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
    <div class="row welcome">

      <div class="input">
        <label for="tamanho">
          <p><i class="bi bi-info"></i>Escolha o tamanho da senha em caracteres:</p>
        </label>
        <input id="tamanho" type="number" bind:value={length}>
        <button on:click={() => generatePassword()}>Gerar Senha</button>
      </div>

      <div class="output">
        {#if password != ''}
          <p>Sua senha gerada é:</p>
          <div class="result">
            <h3 class="{copied?"check":""}">{password}</h3>
            <button class="copy" on:click={() => copy(password)}>
              <i class="bi bi-clipboard{copied?"-check":""}"></i>
            </button>
            {#if copied}
              <p>
                <small class="check">SENHA COPIADA!</small>
              </p>
            {/if}
          </div>
        {/if}    
      </div>
    
    </div>
  </div>
</section>

<style>
  .container {
    padding: 60px 0;
  }

  .row {
    box-shadow: 2px 1px 8px #999;
    border-radius: 4px;
    padding: 10px;
  }

  .input {
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 20px;
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

  .output p {
    text-align: center;
    width: 100%;
  }

  .result {
    display: flex;
    justify-content: center;
    align-items: center;
    flex-wrap: wrap;
  }

  .bi-clipboard-check, .check {
    color: green;
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
    cursor: pointer;
  }
</style>