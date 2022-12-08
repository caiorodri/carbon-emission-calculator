# Carbon Emission Calculator
 Calculadora de Emissão de Carbono criada para uma Atividade Pratica Supervisionada (APS) da faculdade de Ciências de Computação

A calculadora de emissão de carbono foi feita especificamente para empresas

## Passo a Passo

### Inicialização do Programa

Quando iniciado o programa, o usuário tem a escolha de ver os dados de empresas já cadastradas em um arquivo JSON, passar as informações e ver o quanto a empresa dele emitiu no ano, ou encerrar o programa.

![alt text](https://github.com/caiorodri/CarbonEmissionCalculator/blob/main/images/tela_inicial.png)

### Escolha da Empresa

Caso o Usuário escolha ver as empresas já cadastradas, uma tela com todas as empresas que tem no arquivo JSON irá aparecer seguindo um padrão definido pelo criador.

![alt text](https://github.com/caiorodri/CarbonEmissionCalculator/blob/main/images/tela_empresas.png)

### Dados da Empresa Escolhida pelo Usuário

Após o usuário escolher a empresa, todos os dados da empresa irão aparecer. Quase todas as informações que aparecem, são as mesmas que o usuário tem que passar caso escolha ver a emissão da própria empresa.

![alt text](https://github.com/caiorodri/CarbonEmissionCalculator/blob/main/images/tela_dados_empresa.png)

Após o usuário pressionar enter, ele voltará para a tela inicial (A primeira imagem deste README).

### Setor da Empresa

A primeira informação que o usuário terá que passar é o setor da empresa.

![alt text](https://github.com/caiorodri/CarbonEmissionCalculator/blob/main/images/tela_setor_empresa.png)

O usuário pode digitar a opção em que o setor está, ou o nome do setor.
Se o Usuário digitar "0" ou "sair" , ele será redirecionado para a tela inicial.

### Funcionarios

Após o usuário escolher o setor da empresa, ele terá que digitar quantos funcionarios trabalham na empresa dele.

![alt text](https://github.com/caiorodri/CarbonEmissionCalculator/blob/main/images/tela_funcionarios.png)

### Combustivel

O usuário terá que digitar o gasto mensal de combustivel da empresa

![alt text](https://github.com/caiorodri/CarbonEmissionCalculator/blob/main/images/tela_gasto_combustivel.png)

Depois que o usuário digitar o gasto mensal de combustivel da empresa, ele vai ter que escolher o principal combustivel usado pela empresa.

![alt text](https://github.com/caiorodri/CarbonEmissionCalculator/blob/main/images/tela_combustivel.png)

Dependendo da opção que o Usuário escolher, o multiplicador recebe um valor diferente

- Diesel = 0.0042
- Gasolina = 0.003504
- Etanol = 0.000024
- Gás Natural = 0.006708

Esse valor será usado para multiplicar o gasto mensal da empresa e guardado dentro da variavel "annual_issue1"

### Energia

Assim como fez com o combustivel, o usuário terá que fazer com energia também.

![alt text](https://github.com/caiorodri/CarbonEmissionCalculator/blob/main/images/tela_gasto_energia.png)

E depois, escolher uma das opções relacionadas ao uso de energia solar.

![alt text](https://github.com/caiorodri/CarbonEmissionCalculator/blob/main/images/tela_energia_solar.png)

Opção 1 ( Não )
- Se for indústria ou "Outro" = 0.002424
- Senão = 0.002136

Opção 2 ( Sim, compro a minha energia de uma fazenda solar )
- Se for indústria ou "Outro" = 0.000936
- Senão = 0.000816

Opção 3 ( Sim, além de consumir da rede, faço geração própria )
- Se for indústria ou "Outro" = 0.004728
- Senão = 0.004164

Esse valor será usado para multiplicar o gasto de energia e guardado dentro da variavel "annual_issue2"

### Distribuição de funcionarios

O usuário irá escolher uma das opções sobre a distribuição dos funcionarios na empresa

![alt text](https://github.com/caiorodri/CarbonEmissionCalculator/blob/main/images/tela_distribuicao_funcionarios.png)

- Majoritariamente Presencial = 0
- Hibrído = 0.1
- Majoritariamente Remoto = 0.2

Esse valor será usado para multiplicar a quantidade de funcionarios na empresa

### Entregas

A proxima informação é ser passada pelo usuário é q quantidade de entregas realizadas pela empresa

![alt text](https://github.com/caiorodri/CarbonEmissionCalculator/blob/main/images/tela_vendas_frete.png)

O usuário tem opções ou pode digitar a quantidade após escolher a opção "Outros"

Após isso, o usuário irá escolher uma das opções para a distancia da maioria dos consumidores

![alt text](https://github.com/caiorodri/CarbonEmissionCalculator/blob/main/images/tela_consumidores.png)

Se a Empresa for do Setor "Indústria" ou "Outro", será necessário fazer duas contas, então precisará de dois multiplicadores, se não for, precisará de apenas 1

Perto do Meu Município
- Se for Industria ou "Outro" = Multiplicador1 = 0.00432, Multiplicador2 = 0.000171
- Senão Multiplicador1 = 0.0044055 

Dentro do Meu Estado
- Se for Industria ou "Outro", Multiplicador1 = 0.00432, Multiplicador2 = 0.00042
- Senão Multiplicador1 = 0.00453

Em um Estado Vizinho
- Se for Industria ou "Outro", Multiplicador1 = 0.00432, Multiplicador2 = 0.00156
- Senão Multiplicador1 = 0.0051 

Em Outra Região do País
- Se for Industria ou "Outro", Multiplicador1 = 0.00432, Multiplicador2 = 0.0036
- Senão Multiplicador1 = 0.00612 

O Multiplicador1 será usado para multiplicar a quantidade de entregas feita pela empresa

O Multiplicador2 será usado para multiplicar o peso da entrega e depois multiplicar pela quantidade de entregas feitas pela empresa, depois somar com o resultado do Multiplicador1 * quantidade de entregas feitas pela empresa

O resultado será guardado dentro da variavel "annual_issue3"

Se o setor da empresa do usuário for "Industria" ou "Outro", ele terá que passar o peso médio do pacote enviado para entrega (Caso contrario, o peso médio fica como 0)

![alt text](https://github.com/caiorodri/CarbonEmissionCalculator/blob/main/images/tela_peso_frete.png)

### Resultado

Após todo esse processo, vai aparacer a tela com a emissão anual da empresa do usuário, com algumas informações sobre o crédito de carbono.

A emissão anual final, será a soma das três variaveis, "annual_issue1", "annual_issue2", "annual_issue3"

![alt text](https://github.com/caiorodri/CarbonEmissionCalculator/blob/main/images/tela_resultado_final.png)

### Finalização

Caso o usuário escolha a opção "sair", o programa vai ser finalizado aparecendo uma simples mensagem animada para o usuário.
