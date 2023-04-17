<script>
  //TUTORIAL AT: https://www.google.com/search?q=javascript+resize+image&sxsrf=APwXEdehpmAr2DEjrzvbhIoMz_rFOeSq6w%3A1681752830964&ei=_oI9ZPnnOcnZ5OUPk7iUkA8&ved=0ahUKEwj53trAubH-AhXJLLkGHRMcBfIQ4dUDCA8&uact=5&oq=javascript+resize+image&gs_lcp=Cgxnd3Mtd2l6LXNlcnAQAzIFCAAQgAQyBQgAEIAEMggIABCABBDLATIICAAQgAQQywEyCAgAEIAEEMsBMggIABCABBDLATIICAAQgAQQywEyCAgAEIAEEMsBMggIABCABBDLATIICAAQgAQQywE6BAgjECc6CwgAEIAEELEDEIMBOgsIABCKBRCxAxCDAToICAAQgAQQsQM6BggjECcQEzoHCAAQigUQQzoHCC4QigUQQzoICC4QgAQQsQM6CAguELEDEIAEOgsILhCKBRCxAxCDAToLCC4QgAQQsQMQgwE6CggAEIoFELEDEEM6CggAEIAEELEDEAo6CgguEIAEELEDEApKBAhBGABQAFjVNGDsR2gAcAF4A4AB2AqIAbNHkgEQMC4xMC40LjAuMi4zLjMuMZgBAKABAcABAQ&sclient=gws-wiz-serp&bshm=foot/1#fpstate=ive&vld=cid:f01235c3,vid:T7huigh9BNQ
  import {onMount} from "svelte"

  let fileInput
  let widthInput = 0
  let heightInput = 0
  let aspectToggle = true
  let canvas
  let ctx
  let activeImage, originalWidthToHeightRatio

  onMount(()=> {
    ctx = canvas.getContext("2d")

    fileInput.addEventListener("change", (e)=> {
      const reader = new FileReader()

      reader.addEventListener("load", ()=> {
        openImage(reader.result)
      })

      reader.readAsDataURL(e.target.files[0])
    })

    widthInput.addEventListener("change", ()=> {
      if(!activeImage) return
      const heightValue = aspectToggle.checked ? widthInput.value / originalWidthToHeightRatio : heightInput.value
      resize(widthInput.value, heightValue)
    })

    heightInput.addEventListener("change", ()=> {
      if(!activeImage) return
      const widthValue = aspectToggle.checked ? heightInput.value * originalWidthToHeightRatio : widthInput.value
      resize(widthValue, heightInput.value)
    })
  })
  

  function openImage(imageSrc){
    activeImage = new Image()

    activeImage.addEventListener("load", ()=> {
      originalWidthToHeightRatio = activeImage.width / activeImage.height
      
      resize(activeImage.width, activeImage.height)
    })

    activeImage.src = imageSrc
  }


  function resize(width, height) {
    canvas.width = Math.floor(width)
    canvas.height = Math.floor(height)
    widthInput.value = Math.floor(width)
    heightInput.value = Math.floor(height)

    ctx.drawImage(activeImage, 0, 0, Math.floor(width), Math.floor(height))
  }

</script>

<div class="container">

  <div class="resizer">
    <input bind:this={fileInput} type="file" class="file">
    <div class="dimensions">
      <input bind:this={widthInput} type="number" value="0" class="width">
      X
      <input bind:this={heightInput} type="number" value="0" class="height">
    </div>
    <label for="aspect">
      <input  bind:this={aspectToggle} checked type="checkbox" class="aspect">
      Keep aspect ratio
    </label>
    <br>
    <canvas bind:this={canvas} class="canvas" width="200" height="200" style="border: 1px solid;"></canvas>
  </div>

</div>


<style>
  .container {
    padding: 60px 0;
  }


</style>