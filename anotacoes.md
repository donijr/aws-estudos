# Anotações sobre AWS

[[_TOC_]]

## AWS Region e Avaliabilty Zones

Region são locais físicos no globo onde a AWS oferece infraestrutura.

### Diferenças das Regions

- Disponibilidade dos serviços da AWS
- Preços dos serviços da AWS
- Desempenho de Rede
- Compliance
- Sustentabilidade



## Segurança

**Formas de Proteger a conta:**

- Definir Budget.
- Usuário root deve ser usado somente para tarefas de configuração e administração da conta AWS.
- Criar usuários para usar a AWS de vários níveis. Exemplo: administrativo, financeiro, somente visualização.
- Adicionar Fator de Autentificação (MFA) no usuário root.
- Adicionar Fator de Autentificação para todos os usuários.



## Autentificação

Serviços: IAM -> MFA

MFA pode ser 2 tipos: 

- Virtual
- Hardware



## IAM

### Usuários

- Podem ser criados usuários com diferentes privilégios e permissões.
- Recomendado criar um usuário diferente do root para administrar o cotidiano da AWS.
- Cada um usuário pode ter uma ou mais credenciais da AWS abaixo:
  - Acess key -  chave de acesso para utilizar serviços da aws através de scripts, applicações, API, CLI, SDK e outrso fora do console da AWS
  - Password - senha para acessar e gerenciar o console web da AWS
- O usuário pode pertencer ao um grupo. 
- Também pode-se copiar permissões de um usuário já existente ou adicionar politicas existentes diretamente para o usuário
- Na criação do usuário é possível pedir o reset da senha no primeiro acesso.
- No fim da criação de um usuário é disponibilizado um arquivo .csv com dados das credenciais do usuário.

### Politicas

- Existem uma variedade de políticas pré-configuradas que podem ser usadas. 
- As políticas são escritas em formato json.
- Apesar de serem escritas em json no console é visualizado também de forma gráfica
- Existem políticas que podem se sobrepor.

## S3
[Exemplos de politicas de Bucket S3](https://docs.aws.amazon.com/AmazonS3/latest/userguide/example-bucket-policies.html)

### Criando um Buket

Caminho: Amazon S3 -> Buckets -> Create bucket

#### Parte 1
**General configuration**
*Bucket name:*  Nome usado para identificar o bucket, será usado no DNS criado para o bucket. Então use um nome adequado para um DNS/URL

*AWS Region*: Região da AWS para o bucket criado. O preço varia de acordo com a região, então dependendo do uso pode-se escolher um região mais barata, com menor ping , etc. 

*Copy settings from existing bucket - optional:*

**Object Ownership**

ACL = Acess Control Lists

*ACLs disable:* YES :large_blue_circle: ou NO :white_circle:

​	- Dica: Apesar de ser um compenente a mais de segurança pode dar um pouco de trabalho para gernciar e ocasionar alguns problemas não desejados. Então pode deixar ACLs desativados (revisar: o quão complicado e impactos em deixar ACLs desativados)

*ACLs enable:* YES :large_blue_circle: ou NO :white_circle:

**Block Public Acess settings for this bucket**







## Links

[Infraestrutura AWS - Regions](https://aws.amazon.com/pt/about-aws/global-infrastructure/regions_az/)

[Lista de Disponibilidade dos Serviços AWS](https://aws.amazon.com/pt/about-aws/global-infrastructure/regional-product-services/)

[Site para medir latência das Regiões da AWS](https://cloudping.info)

[Sustentabilidade da AWS](https://sustainability.aboutamazon.com/environment/the-cloud)

[Exemplos de politicas de Bucket S3](https://docs.aws.amazon.com/AmazonS3/latest/userguide/example-bucket-policies.html)



## Regiões e Serviços Utilizadas

- S3 - US-EAST-1  Virginia
