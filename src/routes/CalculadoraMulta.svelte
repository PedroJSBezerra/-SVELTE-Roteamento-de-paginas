<script>
  let vArea
  let desconto
  let qtSessoes
  let rSessoes
</script>

<h3>Calculo da Multa por Area</h3>
<main>
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
  
  <div class="resultArea">
    <div class="results">
      <p>Valor da Area:</p>
      <p>R$ {(vArea-vArea*desconto/100).toFixed(2)}</p>
    </div>
    <div class="results">
      <p>Valor Realizado em Sessões:</p>
      <p>R$ {((vArea-vArea*desconto/100)/qtSessoes*rSessoes).toFixed(2)}</p>
    </div>
    <div class="results">
      <p>Valor da Multa:</p>
      <p>R$ {(((vArea-vArea*desconto/100) - ((vArea-vArea*desconto/100)/qtSessoes*rSessoes)) * 0.3).toFixed(2)}</p>
    </div>
  </div>

</main>

<style>
  main{
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
  }
  main > * {
    min-width: 250px;
  }
  .inputArea, .inputArea{
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
    width: 100%;
    flex-direction: column;
    align-items: flex-start;
    margin: 5px 0;
    background: rgba(0,0,0, .25);
    border-radius: 4px;
  }
  p{
    margin: 6px 10px;
  }
</style>