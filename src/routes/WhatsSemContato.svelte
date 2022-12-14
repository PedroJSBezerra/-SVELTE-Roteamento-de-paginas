<script>

  //variaveis globais
  let form
  let phone
  let device
  let number = 0
  const desktopUrl = "https://web.whatsapp.com/send?phone=55"
  const mobileUrl = "https://api.whatsapp.com/send?phone=55"
  let wppUrl

  window.onload = () => {

    // testa se o dispositivo é mobile
    if(/Android|webOS|iPhone|iPad|iPod|BlackBerry|IEMobile|Opera Mini/i.test(navigator.userAgent)){
      // true for mobile device
      device.innerHTML = "Dispositivo Móvel"
      wppUrl = mobileUrl
    }else{
      // false for not mobile device
      device.innerHTML = "Dispositivo Desktop"
      wppUrl = desktopUrl
    }
    //substitui o number e remove caracteres ao digitar
    phone.addEventListener('keyup', (evt) => {
      let temp = evt.target.value.replace(/\(|\)|\-|\s/g, "")
      console.log(temp)
      number = temp
    })
    //funcao de envio redirect
    form.addEventListener('submit', (evt) => {
      evt.preventDefault()
      if(number == "") {
        window.alert("Por favor digite um número!")
        return
      }
      if(number.length < 10) {
        window.alert("Digite um número ex: (ddd)+0000-0000")
        return
      }
      window.open(wppUrl + number, '_blank')
    })
  }

</script>

<section class="section">
  <div class="container">
    <div class="card col-sm-6 m-3">
      <div class="card-header" bind:this={device}></div>
      <form class="card-body" bind:this={form} id="form">
        <h5 class="card-title">Whatsapp Sem Contato</h5>
        <label class="form-label" for="phone">
          <p class="card-text">Digite ou cole o telefone 👇.</p>
        </label>
        <input class="form-control mb-3" bind:this={phone} placeholder="(00)0000-0000" inputmode="numeric" type="phone" id="phone">
        <input class="btn btn-primary" type="submit" value="Abrir Conversa">
      </form>
    </div>  
  </div>
</section>


<style>
</style>