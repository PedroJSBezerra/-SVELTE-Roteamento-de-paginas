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

<div class="welcome box">
  <h1>Whatsapp Sem Contato</h1>
  <div bind:this={device} class="device"></div>
</div>

<form bind:this={form} id="form" class="box">
  <label for="phone">
    <span>Digite ou cole o telefone 👇.</span><br>
  </label>
  <input bind:this={phone} placeholder="(00)0000-0000" inputmode="numeric" type="phone" id="phone">
  <br>
  <input type="submit" value="Abrir Conversa">
</form>