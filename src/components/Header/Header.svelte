<script>
  let menuOpen = false
  let toggle = () => {
    menuOpen = !menuOpen
  }

</script>

<header class="section {menuOpen? "menu open" :"menu close" }" on:click={() => toggle()}>
  
  <div class="button {menuOpen? "open": ""}">
    <span></span>
  </div>
  
  <nav class="container">
    <div class="logo">
      <h3>
        <a href="#/">E-ToolBox</a>
      </h3>
    </div>

    <div style="margin: 0 auto;"></div>
    
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
</header>

<style>

  .button {
    position: fixed;
    right: 32px;
    top: 32px;
    width: 32px;
    height: 32px;
    opacity: 0.7;
    display: flex;
    align-items: center;
    justify-content: center;
  }

  .button span:hover {
    opacity: 1;
  }

  .button span, .button span:before, .button span:after {
    content: ' ';
    position: absolute;
    height: 4px;
    width: 30px;
    background-color: #333;
  }

  .button span:before {
    transform: translateY(-10px);
  }

  .button span:after {
    transform: translateY(10px);
  }

  .button.open span {
    display: none;
  }

  .button.open span:before {
    transform: rotate(-45deg);
  }

  .button.open span:after {
    transform: rotate(45deg);
  }

  .section {
    padding: 40px 0;
  }

  .container {
    margin: 0 20px;
  }

  header {
    box-shadow: 5px 10px 12px 2px rgb(0,0,0, .15);
    position: absolute;
    top: 0;
    width: 100%;
    bottom: 0;
    overflow: hidden;
    transition: left ease-in .15s;
    background: rgb(237 237 237 / 100%);
  }

  .menu.open {
    left: 0;
  }

  .menu.close {
    left: 100%;
  }

  nav, ul{
    display: flex;
  }

  nav {
    margin: 0 auto;
    align-items: center;
    flex-direction: column;
  }

  ul {
    display: flex;
    flex-wrap: wrap;
  }

  li {
    margin: 6px;
  }

  a {
    padding: 4px 6px;
    background: rgb(0 0 0 / 15%);
    border-radius: 4px;
  }

</style>