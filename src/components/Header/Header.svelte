<script>
  import NavOffCanvas from './NavOffCanvas.svelte'
</script>

<header class="container-fluid">
  <nav class="navbar navbar-expand-lg navbar-light bg-white fixed-top">
    <div class="container-fluid">
      <NavOffCanvas/>
    </div>
  </nav>
</header>

<style>
nav {
  box-shadow: 0 10px 20px 0 rgba(0,0,0,.05);
  padding-top: .5625rem;
}

</style>