<script>
  let ValorDaArea = 1000
  let PorcentagemDesconto = 70
  let QuantidadeSessoesVendido = 10
  let QuantidadeSessoesRealizadas = 7
    
  $: ResValorDaArea = ValorDaArea - (ValorDaArea * PorcentagemDesconto/100)
  $: ResValorRealizadoEmSessoes = ResValorDaArea/QuantidadeSessoesVendido*QuantidadeSessoesRealizadas
  $: ResValorDaMulta = ResValorDaArea/QuantidadeSessoesVendido*(QuantidadeSessoesVendido-QuantidadeSessoesRealizadas)*30/100
</script>

<div class="calculadora">
  
  <div class="inputArea">
    <div class="box">
      <h3 class="title">Calculo do cancelamento</h3>
      <h3>Digite os valores</h3>
      <label for="ValorDaArea">Valor da Area / pacote</label>
      <input type="number" id="ValorDaArea" bind:value={ValorDaArea}>
      
      <label for="PorcentagemDesconto">PorcentagemDesconto em %</label>
      <input type="number" id="PorcentagemDesconto" bind:value={PorcentagemDesconto}>

      <label for="QuantidadeSessoesVendido">Qt Sessões vendido</label>
      <input type="number" id="QuantidadeSessoesVendido" bind:value={QuantidadeSessoesVendido}>

      <label for="QuantidadeSessoesRealizadas">Sessões Realizadas</label>
      <input type="number" id="QuantidadeSessoesRealizadas" bind:value={QuantidadeSessoesRealizadas}>
    </div>
  </div>

  <div class="resultArea">
    <div class="box">
      <h3>Resultado</h3>
      <div class="results">
        <p>Valor da Area:</p>
        <p>{'R$ ' + ResValorDaArea.toFixed(2)}</p>
      </div>
      <div class="results">
        <p>Valor Realizado em Sessões:</p>
        <p>{'R$ ' + ResValorRealizadoEmSessoes.toFixed(2)}</p>
      </div>
      <div class="results">
        <p>Valor da Multa:</p>
        <p>{'R$ ' + ResValorDaMulta.toFixed(2)}</p>
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

  .inputArea input {
    height: 40px;
    font-size: 1.2rem;
    border: none;
    outline: none;
    border-radius: 4px;
    margin-bottom: 16px;
    opacity: .9;
    font-weight: 600;
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