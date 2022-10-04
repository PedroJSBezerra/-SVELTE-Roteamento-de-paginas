<script>
  import { location } from "svelte-spa-router"
</script>

<a class="btn btn-primary" data-bs-toggle="offcanvas" href="#offcanvasExample" role="button" aria-controls="offcanvasExample">
  Link with href
</a>

<div class="offcanvas offcanvas-start" tabindex="-1" id="offcanvasExample" aria-labelledby="offcanvasExampleLabel" style="max-width: 300px;">
  <div class="offcanvas-body p-0">
    <div class="d-flex flex-column flex-shrink-0 p-3 bg-light" style="width: 100%; height: 100%;">
      <div class="offcanvas-header">
      <h5 class="offcanvas-title" id="offcanvasExampleLabel">E-ToolBox</h5>
      <button type="button" class="btn-close" data-bs-dismiss="offcanvas" aria-label="Close"></button>
    </div>
    <hr>
    <ul class="nav nav-pills flex-column mb-auto">
      <li class="nav-item" data-bs-dismiss="offcanvas">
        <a href="#/" class="d-flex nav-link {($location=="/")?" active":"link-dark"}">
          <i class="bi bi-house-door pe-none me-2"></i>
          Home
        </a>
      </li>
      <li data-bs-dismiss="offcanvas">
        <a href="#/whatssemcontato" class="d-flex nav-link {($location=="/whatssemcontato")?" active":"link-dark"}">
          <i class="bi pe-none me-2 bi-whatsapp"></i>
          Whats Sem Contato
        </a>
      </li>
      <li data-bs-dismiss="offcanvas">
        <a href="#/calculadoramulta" class="d-flex nav-link {($location=="/calculadoramulta")?" active":"link-dark"}">
          <i class="bi pe-none me-2 bi-calculator"></i>
          Calculadora Multa
        </a>
      </li>
    </ul>
    </div>
  </div>
</div>