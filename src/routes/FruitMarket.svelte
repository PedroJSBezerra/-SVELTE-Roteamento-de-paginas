<!-- <script>
  const data = [
    {
      name: '🍌 banana',
      color: "yellow"
    },
    {
      name: '🍊 orange',
      color: "orange"
    },
    {
      name: '🍎 apple',
      color: "#9a464c"
    },
    {
      name: '🍇 grape',
      color: "#6f2da8"
    },
    {
      name: '🍉 watermelon',
      color: "#e1697c"
    },
    {
      name: '🥥 coco',
      color: "white"
    }
  ]

  let search = ''
  let list= ''

  //get input
  search.addEventListener('keyup', (event) => {
    const imputText = event.target.value
    const filteredData = data.filter(item => {
      return (
        item.name.toLowerCase().includes(imputText.toLowerCase())
      )
    })
    renderList(filteredData)
  })

  //insertion
  const renderList = (data) => {  
    //color change
    (data.length == 1)? 
    document.body.style.backgroundColor = data[0].color : 
    document.body.style.backgroundColor= "cyan"
    //list change
    list.innerHTML = data.map(item => `<li>${item.name}</li>`).join('')
  }

  renderList(data)

</script>

<div class="box">
  <input bind:this={search} type="text" id='search' placeholder="🔎 Search here...">
  <ul bind:this={list} id="list"></ul>
</div>

<style>

  * {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
  }
  body {
    display: grid;
    place-items: center;
    background: cyan;
    transition: all .25s ease;
  }

  .box {
    position: absolute;
    top: 50%;
    transform: translateY(-50%);
    background: white;
    display: flex;
    flex-direction: column;
    width: 250px;
    min-height: 90vh;
    padding: 20px;
    gap: 20px;
    border-radius: 20px;
    box-shadow: 
      0 0 1px white,
      0 0 3px white,
      1px 2px 12px #333;
  }

  ul {
    list-style: none;
    display: flex;
    flex-direction: column;
    gap: 16px;
  }

  input {
    font-size: 1.2rem;
  }

  li:hover {
    background: #ddd;
    cursor: pointer;
    transform: scale(1.06);
    box-shadow: 1px 3px 3px #aaa, 0px 0px 26px #ddd;
  }

  li, input {
    transition: all .18s ease-out;
    background: #eee;
    padding: 6px;
    border-radius: 4px;
  }

</style> -->