# calculo-de-saldo-
aula básica de programação - desafio 6 

const usuarios = [
    {
      nome: "Salvio",
      receitas: [115.3, 48.7, 98.3, 14.5],
      despesas: [85.3, 13.5, 19.9]
    },
    {
      nome: "Marcio",
      receitas: [24.6, 214.3, 45.3],
      despesas: [185.3, 12.1, 120.0]
    },
    {
      nome: "Lucia",
      receitas: [9.8, 120.3, 340.2, 45.3],
      despesas: [450.2, 29.9]
    }
  ];
//funçao que pega os numeros no array colocado nela e soma deles
  function somaNumeros(numeros){
   //variavel soma começa a contagem no zero
    let soma = 0 
   /*para cada variaçao dos numeros colocados dentro da funçao
    a variavel numero é somada com a variavel soma*/
    for (let numero of numeros)/*faça*/{
       soma = soma + numero

    }
    return soma 
}
// aplica a funçao acima na receita para somar os dados dos arrays receitas e despesas
function calculoDeSaldo(receitas, despesas){
    const somaDeReceitas = somaNumeros(receitas)
    const somaDeDespesas = somaNumeros(despesas)
//calcula a diferença do saldo 
    const saldo = somaDeReceitas - somaDeDespesas
    return saldo
}

//para cada objeto do array usuarios aplique a funçao calculoDeSaldo
for ( let pessoa of usuarios) {
    const saldoFinal = calculoDeSaldo(pessoa.receitas, pessoa.despesas)

//se o saldo for maior que zero ...
if (saldoFinal > 0){
    console.log(`${pessoa.nome} seu saldo esta positivo`)
}
//... se nao ...
  else{
    console.log(`${pessoa.nome} seu saldo esta negativo`)
  }
}
