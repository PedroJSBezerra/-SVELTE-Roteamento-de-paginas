<script>
  import { onMount } from "svelte"
  let textArea

  onMount(()=>{
    window.addEventListener("dragover", dragOverHandler)
    window.addEventListener("drop", dropHandler)

    function dragOverHandler(ev) {
      ev.preventDefault();
    }

    function dropHandler(ev) {
      ev.preventDefault();
      textArea.textContent = ""
      Array.from(ev.dataTransfer.files).map(file=>{
        let index = file.name.lastIndexOf(".") + 1
        let fileName = file.name.slice(0, index)
        textArea.textContent += file.name+"\n"
      })
    }
  })

</script>

<div class="fileNameExtractor">
  <h3>Solte os arquivos para extrair os nomes:</h3>
  <textarea bind:this={textArea} class="textArea" name="" id="" cols="30" rows="10"></textarea>
</div>

<style>
  :global(body) {
    margin: 0;
    padding: 0;
  }

  .fileNameExtractor {
    width: 100vw;
    height: 100vh;
    display: flex;
    align-items: center;
    justify-content: center;
    flex-direction: column;
  }

  .textArea {
    width: 80%;
    height: 80%;
    font-family: Inter, system-ui, Avenir, Helvetica, Arial, sans-serif;
  }
</style>