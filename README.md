# Buscar-CEP-JS

<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <title>Buscar CEP</title>
</head>
<body>
    <h1> Buscar Endereço Pelo CEP</h1>
    <input type="text" id="cep" placeholder="Digite o CEP">
    <button onclick="buscarCep()">Buscar</button>
    <p id="resultado"></p>
    <script>
        async function buscarCep(){
            const cep =document.getElementById("cep").value;
            const resposta = await fetch(`https://viacep.com.br/ws/${cep}/json/`)
            const endereco = await resposta.json();
            document.getElementById("resultado").innerHTML = `
                Rua: ${endereco.logradouro}<br>
                Bairro: ${endereco.bairro}<br>
                Cidade: ${endereco.localidade}<br>
                Estado: ${endereco.uf}<br>
        `
     }
    </script>

</body>+
</html>
