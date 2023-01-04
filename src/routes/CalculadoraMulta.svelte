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

<div class="calculadora">
  
  <div class="inputArea">
    <div class="box">
      <h3 class="title">Calculo do cancelamento</h3>
      <h3>Digite os valores</h3>
      <label for="vArea">Valor da Area / pacote</label>
      <input type="number" id="vArea" bind:value={vArea}>
      
      <label for="desconto">Desconto em %</label>
      <input type="number" id="desconto" bind:value={desconto}>

      <label for="qtSessoes">Qt Sessões vendido</label>
      <input type="number" id="qtSessoes" bind:value={qtSessoes}>

      <label for="rSessoes">Sessões Realizadas</label>
      <input type="number" id="rSessoes" bind:value={rSessoes}>
    </div>
  </div>

  <div class="resultArea">
    <div class="box">
      <h3>Resultado</h3>
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

<style>

  .calculadora {
    align-items: center;
    display: flex;
    flex-wrap: wrap;
    height: 100vh;
    background: #4B2C8D;
  }

  .title {
    text-align: center;
    width: 100%;
    padding: 20px 0;
  }

  .inputArea, .resultArea {
    height: 100%;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    padding: 20px;
  }

  .inputArea {
    min-width: 70%;
    color: white;
  }

  .inputArea .box {
    display: flex;
    flex-direction: column;
    width: 300px;
  }

  .resultArea {
    background: #fff;
    width: 30%;
  }
  

  @media screen and (max-width: 424px) {
    .resultArea {
      max-width: 100%;
    }
  }

  @media screen and (min-width: 425px) and (max-width: 767px) {
  }

  @media screen and (min-width: 768px) and (max-width: 1023px) {
  }

  @media screen and (min-width: 1024px) {
  }

</style>