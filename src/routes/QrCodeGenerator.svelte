<script>
  //https://www.npmjs.com/package/qrcode-generator
  import qrcode from 'qrcode-generator';

  //Niveis de correção
  let correctionLevels = ['L', 'M', 'Q', 'H']
  //Tamanho da imagem
  let tamanhoDaImagem = 8

  var typeNumber = 4;
  var errorCorrectionLevel = 'L';
  var qr = qrcode(typeNumber, errorCorrectionLevel);

  let img
  let dataUrl

  let imputUrl

  let createQr = (imputUrl) => {
    qr.addData(imputUrl);
    qr.make();
    img = qr.createImgTag(tamanhoDaImagem)
    dataUrl = qr.createDataURL(tamanhoDaImagem)
    console.log(dataUrl)
  }

</script>

<section class="section">
  <div class="container welcome">
    <form on:submit|preventDefault action="">
      <h3>Gerador de QrCode</h3>
      <label for="imputUrl">Digite seu texto para gerar o QrCode:</label><br>
      <input id="imputUrl" type="text" bind:value={imputUrl}><br><br>
      <button on:click={() => createQr(imputUrl)}>Gerar QR code</button>
    </form>
    <img src="{dataUrl}" alt="">
  </div>
</section>

<style>
  div img {
    width: 300px;
    height: 300px;
  }
</style>