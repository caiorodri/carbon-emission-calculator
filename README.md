# Carbon Emission Calculator  

Calculadora de Emissão de Carbono desenvolvida para uma Atividade Prática Supervisionada (APS) no curso de Ciência da Computação.  

A ferramenta foi projetada especificamente para empresas que desejam calcular e monitorar suas emissões anuais de carbono.  

## Passo a Passo  

### Inicialização do Programa  

Ao iniciar o programa, o usuário pode:  
- Visualizar os dados de empresas cadastradas em um arquivo JSON;  
- Inserir informações da própria empresa para calcular suas emissões anuais de carbono;  
- Encerrar o programa.  

![Tela Inicial](https://github.com/caiorodri/CarbonEmissionCalculator/blob/main/images/tela_inicial.png)  

### Escolha da Empresa  

Caso o usuário opte por visualizar as empresas cadastradas, será exibida uma lista contendo todas as empresas armazenadas no arquivo JSON, seguindo um padrão predefinido.  

![Tela Empresas](https://github.com/caiorodri/CarbonEmissionCalculator/blob/main/images/tela_empresas.png)  

### Dados da Empresa Selecionada  

Após a escolha da empresa, todas as suas informações serão exibidas. Essas informações são praticamente as mesmas que o usuário precisará fornecer caso decida calcular a emissão de carbono da própria empresa.  

![Tela Dados da Empresa](https://github.com/caiorodri/CarbonEmissionCalculator/blob/main/images/tela_dados_empresa.png)  

Após pressionar "Enter", o usuário será redirecionado para a tela inicial.  

### Setor da Empresa  

A primeira informação solicitada é o setor de atuação da empresa.  

![Tela Setor da Empresa](https://github.com/caiorodri/CarbonEmissionCalculator/blob/main/images/tela_setor_empresa.png)  

O usuário pode inserir o número correspondente à opção desejada ou digitar o nome do setor. Caso digite "0" ou "sair", retornará à tela inicial.  

### Funcionários  

Em seguida, o usuário deverá informar a quantidade de funcionários que trabalham na empresa.  

![Tela Funcionários](https://github.com/caiorodri/CarbonEmissionCalculator/blob/main/images/tela_funcionarios.png)  

### Consumo de Combustível  

O usuário deverá inserir o gasto mensal com combustível da empresa.  

![Tela Gasto Combustível](https://github.com/caiorodri/CarbonEmissionCalculator/blob/main/images/tela_gasto_combustivel.png)  

Em seguida, será necessário selecionar o principal tipo de combustível utilizado.  

![Tela Escolha do Combustível](https://github.com/caiorodri/CarbonEmissionCalculator/blob/main/images/tela_combustivel.png)  

Cada tipo de combustível possui um fator de emissão diferente:  

- **Diesel** = 0.0042  
- **Gasolina** = 0.003504  
- **Etanol** = 0.000024  
- **Gás Natural** = 0.006708  

Esse fator será utilizado para calcular as emissões e armazenado na variável `annual_issue1`.  

### Consumo de Energia  

O usuário também deverá inserir o gasto mensal com energia elétrica.  

![Tela Gasto Energia](https://github.com/caiorodri/CarbonEmissionCalculator/blob/main/images/tela_gasto_energia.png)  

Em seguida, deve informar se a empresa utiliza energia solar.  

![Tela Energia Solar](https://github.com/caiorodri/CarbonEmissionCalculator/blob/main/images/tela_energia_solar.png)  

Os multiplicadores variam conforme a escolha:  

**Opção 1 (Não utiliza energia solar)**  
- Indústria/Outro: **0.002424**  
- Outros setores: **0.002136**  

**Opção 2 (Compra energia de uma fazenda solar)**  
- Indústria/Outro: **0.000936**  
- Outros setores: **0.000816**  

**Opção 3 (Utiliza geração própria, além da rede elétrica)**  
- Indústria/Outro: **0.004728**  
- Outros setores: **0.004164**  

O fator correspondente será multiplicado pelo consumo de energia e armazenado na variável `annual_issue2`.  

### Modelo de Trabalho  

O usuário deve selecionar a opção que melhor representa o modelo de trabalho da empresa.  

![Tela Distribuição Funcionários](https://github.com/caiorodri/CarbonEmissionCalculator/blob/main/images/tela_distribuicao_funcionarios.png)  

Cada modelo possui um fator de impacto:  

- **Majoritariamente Presencial** = 0  
- **Híbrido** = 0.1  
- **Majoritariamente Remoto** = 0.2  

Esse valor será multiplicado pelo número de funcionários da empresa.  

### Entregas  

A próxima etapa envolve o número de entregas realizadas pela empresa.  

![Tela Vendas e Frete](https://github.com/caiorodri/CarbonEmissionCalculator/blob/main/images/tela_vendas_frete.png)  

O usuário pode selecionar uma opção predefinida ou inserir manualmente a quantidade de entregas na opção "Outros".  

Em seguida, será necessário indicar a localização da maioria dos consumidores.  

![Tela Consumidores](https://github.com/caiorodri/CarbonEmissionCalculator/blob/main/images/tela_consumidores.png)  

Os multiplicadores variam conforme a localização e setor da empresa:  

| Localização dos Consumidores  | Indústria/Outro (Multiplicador 1) | Indústria/Outro (Multiplicador 2) | Outros setores |
|------------------------------|----------------------------------|----------------------------------|----------------|
| **Próximo ao município**      | 0.00432                         | 0.000171                         | 0.0044055       |
| **Dentro do estado**          | 0.00432                         | 0.00042                          | 0.00453        |
| **Em estado vizinho**         | 0.00432                         | 0.00156                          | 0.0051         |
| **Outra região do país**      | 0.00432                         | 0.0036                           | 0.00612        |

- **Multiplicador 1**: Usado para calcular o impacto das entregas.  
- **Multiplicador 2**: Aplicado apenas para empresas do setor "Indústria" ou "Outro", considerando também o peso médio do pacote.  

Caso necessário, o usuário deverá informar o peso médio dos pacotes enviados.  

![Tela Peso Frete](https://github.com/caiorodri/CarbonEmissionCalculator/blob/main/images/tela_peso_frete.png)  

A variável `annual_issue3` armazenará o resultado desse cálculo.  

### Resultado Final  

Ao concluir todas as etapas, será exibido o resultado final com a emissão anual da empresa e informações sobre créditos de carbono.  

A emissão total será calculada somando:  
`annual_issue1 + annual_issue2 + annual_issue3`  

![Tela Resultado Final](https://github.com/caiorodri/CarbonEmissionCalculator/blob/main/images/tela_resultado_final.png)  

### Finalização  

Se o usuário optar por encerrar o programa, será exibida uma mensagem animada de despedida.  
