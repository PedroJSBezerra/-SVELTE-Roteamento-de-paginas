<script>
  let open = false
  let toggle = () => {
    open = !open
  }

</script>

<header class="header">
  <div class="container">
    
    <div class="button {open? "open": ""}" on:click={() => toggle()}>
      <span></span>
      <span></span>
      <span></span>
    </div>

    <div class="logo">
      <h3>
        <a href="#/">E-ToolBox</a>
      </h3>
    </div>

    <div style="width: 40px;"></div>
    
    <nav class="nav {open? "open":""}" on:click={() => toggle()}>
      <div class="nav container">
        <h3 style="margin: 0 20px;{open? "":"display: none:"}">Menu</h3>
        <hr>
        <ul class="menu">
          <li>
            <a href="#/">
              <i class="bi bi-house-door pe-none me-2"></i>
              Home
            </a>
          </li>

          <li>
            <a href="#/whatssemcontato">
              <i class="bi pe-none me-2 bi-whatsapp"></i>
              Whats Sem Contato
            </a>
          </li>
          
          <li>
            <a href="#/calculadoramulta">
              <i class="bi pe-none me-2 bi-calculator"></i>
              Calculadora Multa
            </a>
          </li>
          
          <li>
            <a href="#/qrcodegenerator">
              <i class="bi bi-qr-code"></i>
              Gerador de Qr Code
            </a>
          </li>
        </ul>
      </div>
    </nav>
  </div>
</header>

<div style="margin-bottom: 60px;"></div>

<style>

  .button {
    align-items: center;
    border-radius: 4px;
    cursor: pointer;
    display: flex;
    height: 40px;
    justify-content: center;
    overflow: hidden;
    width: 40px;
    z-index: 999;
    position: relative;
  }

  .button span,
  .button span:nth-child(1),
  .button span:nth-child(2) {
    background: #333;
    border-radius: 2px;
    content: "";
    display: block;
    height: 3px;
    position: absolute;
    transition: all .3s ease-in-out; 
    width: 25px;
    border-radius: 2px;
  }

  .button span:nth-child(1){
    transform: translateY(-9px);
  }

  .button span:nth-child(2){
    transform: translateY(9px);
  }

  .button.open span {
    transform: translateX(50px);
  }

  .button.open span:nth-child(1){
    transform: translateY(0) rotate(-45deg);
  }

  .button.open span:nth-child(2){
    transform: translateY(0) rotate(45deg);
  }

  header {
    padding: 10px 0;
    box-shadow: 0 0 6px -4px;
    height: 60px;
    z-index: 999;
    position: fixed;
    top: 0;
    right: 0;
    left: 0;
    background: #fff;
    margin-bottom: 25px;
  }

  .container {
    display: flex;
    align-items: center;
    justify-content: space-between;
  }

  nav {
    background: #ddd;
    position: fixed;
    top: 0;
    bottom: 0;
    right: 100%;
    width: 100%;
    transition: right .4s;
    padding: 60px 0;
  }

  .nav.container {
    flex-direction: column;
  }

  nav.open {
    right: 0;
  }

  nav ul {
    margin: 0 auto;
    padding: 0 10px;
  }

  nav ul li a {
    display: block;
    padding: 6px 8px;
    font-size: 1.2rem;
  }

</style>