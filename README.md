# WhatsappBot



### SCRIPT para verificar se o contato existe ou não

var lista = [
'5581996429878'
,'5592999603373'
,'5581921213400'
,'5581999119454'
]

document.body.insertAdjacentHTML('beforeend',`<a href="https://wa.me/${item}" id="wppLnkDL">link</a>`)



var link = document.getElementById('wppLnkDL')

var existeNumber = []
var naoExisteNumber = []

var sleep = (ms) => new Promise((resolve)=>setTimeout(resolve, ms))


var contatoExiste = (number) => {

  if(document.querySelector('._3J6wB')){
    naoExisteNumber.push(number)
  }else{
    existeNumber.push(number)
  }

}


var testeContatos = async () => {

  for await (var item of lista) {
    console.log(item)
    link.href=`https://wa.me/${item}`
    await sleep(1000)
    link.click()
    await sleep(2000)

    if(document.querySelector('._1bpDE')){
      a = true
      while (a){
        console.log("Aguarde")

        if(document.querySelector('._1bpDE'))
          a = false

        await sleep(1000)
      }

      contatoExiste(item)
      

    }else{
      contatoExiste(item)
    }

  }

  console.log("Existem")
  console.log(existeNumber)
  console.log("------------")
  console.log("Não existem")
  console.log(naoExisteNumber)

  console.log(`Existem: ${existeNumber.length}`, `Não existem: ${naoExisteNumber.length}`)

}

testeContatos()
