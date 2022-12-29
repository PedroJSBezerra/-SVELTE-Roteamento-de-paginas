<script>
  let vArea
  let desconto
  let qtSessoes
  let rSessoes
  
  let valorArea = (vArea, desconto) => {
    let total = vArea - (vArea * desconto /100)
    return isNaN(total)? "" : total.toFixed(2)
  }

  let valorRealizado = (vArea, qtSessoes, rSessoes) => {
    let total = (valorArea(vArea, desconto)/qtSessoes) * rSessoes
    return isNaN(total)? "" : total.toFixed(2)
  }

  let valorDaMulta = (vArea, qtSessoes, rSessoes) => {
    let total = (vArea/qtSessoes) * (qtSessoes - rSessoes) * 0.3
    return isNaN(total)? "" : total.toFixed(2)
  }

</script>

<section class="section">
  <div class="container">
    <div class="row">

      <div class="calculadora">
        <h3>Calculo do cancelamento</h3>
        <p>Digite os valores</p>
        
        <div class="inputArea">
          <label for="vArea">Valor da Area / pacote</label>
          <input type="number" id="vArea" bind:value={vArea}><br>
          
          <label for="desconto">Desconto em %</label>
          <input type="number" id="desconto" bind:value={desconto}><br>

          <label for="qtSessoes">Qt Sessões vendido</label>
          <input type="number" id="qtSessoes" bind:value={qtSessoes}><br>

          <label for="rSessoes">Sessões Realizadas</label>
          <input type="number" id="rSessoes" bind:value={rSessoes}><br>
        </div>
        <h3>Resultado</h3>
        <div class="resultArea">
          <div class="results">
            <p>Valor da Area:</p>
            <p>R$ {valorArea(vArea,desconto)}</p>
          </div>
          <div class="results">
            <p>Valor Realizado em Sessões:</p>
            <p>R$ {valorRealizado(vArea, qtSessoes, rSessoes)}</p>
          </div>
          <div class="results">
            <p>Valor da Multa:</p>
            <p>R$ {valorDaMulta(vArea, qtSessoes, rSessoes)}</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</section>

<style>
  
  .calculadora {
    background: rgba(0,0,0, .15);
    padding: 20px;
    border-radius: 8px;
  }

  .inputArea {
    display: flex;
    flex-direction: column;
    align-items: flex-start;
  }

  .resultArea{
    display: flex;
    flex-direction: column;
    justify-content: space-evenly;
  }

  .results{
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    margin: 5px 0;
    background: rgba(0,0,0, .15);
    border-radius: 4px;
  }

  .results p{
    margin: 6px 10px;
  }

  @media only screen and (max-width: 425px) {
  }

  

  
</style>