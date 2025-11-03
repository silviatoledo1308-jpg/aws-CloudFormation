from pathlib import Path

## Desafio DIO – Infraestrutura Automatizada com AWS CloudFormation

## Sobre o Projeto

Este repositório foi desenvolvido como parte do desafio da **Digital Innovation One (DIO)**, com o objetivo de aplicar os conceitos de **Infraestrutura como Código (IaC)** por meio do **AWS CloudFormation**.  
Durante este laboratório, foi utilizada uma pilha automatizada do CloudFormation para iniciar um pipeline do **Amazon Forecast**, responsável por gerar previsões baseadas em um conjunto de dados de demonstração.

O projeto demonstra o uso prático do CloudFormation para provisionar e gerenciar recursos da AWS automaticamente, explorando seus benefícios em comparação a outras ferramentas de IaC, como o Terraform, e os formatos suportados para criação de modelos (YAML e JSON).

---

## Objetivos de Aprendizagem

- Aplicar os conceitos de Infraestrutura como Código em um ambiente prático.  
- Implantar uma pilha AWS CloudFormation automatizada com Amazon Forecast.  
- Compreender os benefícios do CloudFormation e suas diferenças em relação ao Terraform.  
- Documentar o processo técnico de forma estruturada e clara.  
- Utilizar o GitHub como ferramenta de documentação e versionamento.

---

## Arquitetura da Solução

A pilha AWS CloudFormation utilizada neste laboratório automatiza a implantação de um pipeline do **Amazon Forecast**, incluindo as seguintes etapas:

1. **Implantação do modelo "Improving Forecast Accuracy with Machine Learning"** via CloudFormation.  
2. **Provisionamento automático** de conjuntos de dados de demonstração (dados de táxis de Nova York) em um bucket do **Amazon S3**.  
3. **Inicialização do pipeline de previsão** no Amazon Forecast, utilizando séries temporais de destino, séries temporais relacionadas e metadados de itens.  
4. **Automação do fluxo completo** de ingestão de dados, treinamento de modelo e geração de previsões.  

O diagrama da solução apresenta as etapas de preparação de dados, ingestão, previsão e avaliação dentro do pipeline do Amazon Forecast.

---

## Benefícios do AWS CloudFormation

- Automação completa: Provisionamento e gerenciamento automatizado de recursos na AWS.  
- Reprodutibilidade: Infraestrutura pode ser recriada de forma idêntica em diferentes ambientes.  
- Gerenciamento em pilhas: Facilita a visualização e manutenção de recursos relacionados.  
- Controle de versionamento: Modelos de infraestrutura podem ser versionados e armazenados em repositórios Git.  
- Suporte a múltiplos formatos: Modelos podem ser escritos em YAML ou JSON.  

---

## Diferença entre AWS CloudFormation e Terraform

| Aspecto | AWS CloudFormation | Terraform |
|----------|-------------------|------------|
| Fornecedor | Exclusivo da AWS | Multi-cloud |
| Linguagem | YAML ou JSON | HCL (HashiCorp Configuration Language) |
| Gerenciamento de Estado | Automático (integrado à AWS) | Manual, via arquivos de estado |
| Reutilização de código | Suporte limitado | Modular e reutilizável |
| Integração com AWS | Nativa | Por meio de provedores externos |

---

## Pré-requisitos

1. Conta ativa na **AWS**.  
2. Acesso ao **console AWS CloudFormation**.  
3. Modelo AWS CloudFormation instalado na região desejada.  

Regiões disponíveis para implantação:
- Tóquio: `ap-northeast-1`  
- Seul: `ap-northeast-2`  
- Mumbai: `ap-south-1`  
- Cingapura: `ap-southeast-1`  
- Sydney: `ap-southeast-2`  
- Frankfurt: `eu-central-1`  
- Irlanda: `eu-west-1`  
- N. da Virgínia: `us-east-1`  
- Ohio: `us-east-2`  
- Oregon: `us-west-2`

---

## Etapas de Implantação

### Etapa 1 – Acesso ao AWS CloudFormation
Acesse o console do AWS CloudFormation e selecione a opção **Create Stack**.  
Na tela de criação, insira a URL do modelo do Amazon Forecast.

### Etapa 2 – Configuração de Parâmetros
Forneça um endereço de e-mail para receber notificações e utilize os valores padrão para os campos de dataset.  
Os campos do console são automaticamente preenchidos com as localizações S3 dos conjuntos de dados de demonstração.

### Etapa 3 – Permissões e Capacidades
Na seção **Capabilities**, marque as opções que autorizam o CloudFormation a criar recursos **IAM** e pilhas aninhadas.  
Confirme clicando em **Create Stack**.

### Etapa 4 – Implantação da Pilha
O CloudFormation implantará automaticamente:
- A solução “Improving Forecast Accuracy with Machine Learning”;  
- O bucket S3 com os dados de táxis de Nova York;  
- O pipeline do Amazon Forecast para geração de previsões.  

---

## Uso com Dados Próprios

Após a execução bem-sucedida do tutorial com dados de demonstração, é possível reutilizar a mesma pilha para gerar previsões com dados próprios.  
Basta substituir os caminhos S3 na etapa de **Configuração de conjuntos de dados** (Etapa 2) pelo endereço de seus próprios arquivos.

---

## Limpeza de Recursos

- A exclusão da pilha de demonstração mantém a pilha “Improving Forecast Accuracy with Machine Learning”.  
- A exclusão desta pilha retém os dados armazenados no **Amazon S3**, **Athena**, **QuickSight** e **Forecast**.  
- Para limpar completamente os recursos, é necessário remover manualmente esses componentes no console da AWS.

---

## Aprendizados e Conclusões

Durante este desafio, foi possível compreender de forma prática:
- A automação de infraestrutura por meio de AWS CloudFormation.  
- A importância da padronização e versionamento de infraestrutura.  
- As diferenças entre ferramentas IaC (CloudFormation vs Terraform).  
- O uso de formatos JSON para definição de recursos na AWS.  
- A criação e execução de pipelines automatizados para o Amazon Forecast.  

O exercício reforça a importância do CloudFormation como uma ferramenta nativa e robusta para gestão de infraestrutura na AWS, permitindo o provisionamento de recursos de forma previsível e auditável.

---

## 👩‍💻 Autora **Silvia Toledo**

---

## 🔗 Referências

- AWS CloudFormation Documentation: [https://docs.aws.amazon.com/cloudformation/](https://docs.aws.amazon.com/cloudformation/)  
- Amazon Forecast Documentation: [https://docs.aws.amazon.com/forecast/](https://docs.aws.amazon.com/forecast/)  
- AWS Sample Solution – Improving Forecast Accuracy with Machine Learning: [https://aws.amazon.com/solutions/implementations/improving-forecast-accuracy-with-machine-learning/](https://aws.amazon.com/solutions/implementations/improving-forecast-accuracy-with-machine-learning/)  
- Digital Innovation One (DIO): [https://www.dio.me/](https://www.dio.me/)
"""


