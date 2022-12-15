<script>
  let open = false
  let toggle = () => {
    open = !open
  }

</script>

<header class="section">
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
    
    <nav class="nav {open? "open":""}" on:click={() => toggle()}>

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
      </ul>
    </nav>
  </div>
  
</header>

<style>

  .button {
    align-items: center;
    background: #fff;
    border-radius: 4px;
    box-shadow: 
      0 0 1px 1px #fff, 
      0 0 2px 3px #f2f2f2, 
      0px 0px 3px 0px #f3f3f3, 
      2px 3px 8px 0px #f9f9f9;
    cursor: pointer;
    display: flex;
    height: 40px;
    justify-content: center;
    overflow: hidden;
    position: fixed;
    right: 20px;
    top: 20px;
    width: 40px;
    z-index: 999;
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
    transform: translateX(-50px);
  }

  .button.open span:nth-child(1){
    transform: translateY(0) rotate(45deg);
  }

  .button.open span:nth-child(2){
    transform: translateY(0) rotate(-45deg);
  }

  nav {
    background: #ddd;
    position: fixed;
    top: 0;
    bottom: 0;
    left: 100%;
    width: 100%;
    transition: left .4s;
    padding: 60px 0;
  }

  nav.open {
    left: 0;
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