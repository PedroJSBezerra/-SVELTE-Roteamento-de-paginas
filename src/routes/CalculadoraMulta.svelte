<script>
  let ValorDaArea = 1000
  let PorcentagemDesconto = 70
  let QuantidadeSessoesVendido = 10
  let QuantidadeSessoesRealizadas = 7
    
  $: ResValorDaArea = ValorDaArea - (ValorDaArea * PorcentagemDesconto/100)
  $: ResValorRealizadoEmSessoes = ResValorDaArea/QuantidadeSessoesVendido*QuantidadeSessoesRealizadas
  $: ResValorDaMulta = ResValorDaArea/QuantidadeSessoesVendido*(QuantidadeSessoesVendido-QuantidadeSessoesRealizadas)*30/100

  let newWindow = () => {
    window.open("https://e-tool-box.vercel.app/#/calculadoramulta", 'mywin','left=900,top=300,width=350,height=400,toolbar=0,resizable=0'); 
    return false;
  }
</script>

<div class="calculadora">
  
  <div class="inputArea">
    <div class="newWindow">
      <button on:click={() => newWindow()}>Abrir em Nova Janela</button>
    </div>
    <h3 class="title">Valores</h3>
    <div class="box">
      
      <label for="ValorDaArea">
        Valor da Area <br>
        <input type="number" id="ValorDaArea" bind:value={ValorDaArea}>
      </label>
      
      <label for="PorcentagemDesconto">
        Desconto % <br>
        <input type="number" id="PorcentagemDesconto" bind:value={PorcentagemDesconto}>
      </label>

      <label for="QuantidadeSessoesVendido">
        Sessões <br>
        <input type="number" id="QuantidadeSessoesVendido" bind:value={QuantidadeSessoesVendido}>
      </label>

      <label for="QuantidadeSessoesRealizadas">
        Realizado em sessões <br>
        <input type="number" id="QuantidadeSessoesRealizadas" bind:value={QuantidadeSessoesRealizadas}>
      </label>

    </div>
  </div>

  <div class="resultArea">
    <h3>Resultado</h3>
    <div class="box">
      <div class="results">
        <div>Valor da Area:</div>
        <div>{'R$ ' + ResValorDaArea.toFixed(2)}</div>
      </div>
      <div class="results">
        <div>R. Sessões:</div>
        <div>{'R$ ' + ResValorRealizadoEmSessoes.toFixed(2)}</div>
      </div>
      <div class="results">
        <div>Multa:</div>
        <div>{'R$ ' + ResValorDaMulta.toFixed(2)}</div>
      </div>
    </div>
  </div>

</div>

<style>
  .calculadora {
    padding: 60px 16px 0;
  }

  .calculadora .inputArea {
    margin-top: 20px;
  }

  .calculadora .inputArea .box {
    display: flex;
    flex-wrap: wrap;
  }

  .calculadora .inputArea .box label {
    margin-right: 6px;  
  }

  .calculadora .inputArea .box label input {
    max-width: 75px;
  }

  .calculadora .resultArea {
    margin-top: 20px;
  }

  .resultArea .box {
    display: flex;
    flex-wrap: wrap;
  }

  .resultArea .box .results {
    background: rgba(0,0,0, .1);
    padding: 6px;
    margin: 6px 6px 6px 0;
    border-radius: 4px;
  }
</style>