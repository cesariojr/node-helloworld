# IBM Talk'n' Labs | DEVOPS

- [IBM Talk'n' Labs | DEVOPS](#ibm-talkn-labs--devops)
  - [Para te ajudar](#para-te-ajudar)
  - [Introdução](#introdu%c3%a7%c3%a3o)
  - [Pré-requisitos](#pr%c3%a9-requisitos)
  - [1 - Criando uma toolchain](#1---criando-uma-toolchain)
  - [2 - Alterando sua aplicação](#2---alterando-sua-aplica%c3%a7%c3%a3o)
  - [3 - Entendendo o Delivery Pipeline](#3---entendendo-o-delivery-pipeline)
  - [6 - Deletar o projeto](#6---deletar-o-projeto)
  - [Material de apoio](#material-de-apoio)
  - [Troubleshooting](#troubleshooting)
  - [License](#license)

## Para te ajudar
* [Troubleshooting](#troubleshooting)
## Introdução
Verificar com o Zé Maria
Uma toolchain é uma coleção de ferramentas que ajudam no desenvolvimento, deploy e tarefas operacionais. Neste Lab, vamos criar uma toolchain a partir de um template para subir uma aplicação em Cloud Foundry. Este template possui um conjunto de ferramentas integradas e um codigo simples de um 'Hello World' em NodeJS. Esta toolchain é pre configurada para ocntinuous delivery, source control, issue tracking e edição de codigo online. 

<!-- O Banco do Brasil, maior banco da América Latina, com destaque em segmentos como agronegócio, infraestrutura, micro e pequenas empresas.
O seu maior propósito é estar próximo das pessoas e ajudar a preservar o que é importante para seus clientes, acionistas, funcionários e toda a sociedade.
Por esta razão, pensando no pequeno e médio agricultor, que muitas vezes não tem acesso, desconhece ou não tem capacidade financeira para contratar soluções robustas que os auxiliem na gestão e monitoramento de seus processos produtivos, o Banco do Brasil quer desenvolver solução de baixo custo, para que estes proprietários através do controle de temperatura e umidade do solo, possam planejar melhor sistemas de irrigação baseado no tipo do produto, além de sistema de reconhecimento de pragas e qualidade do plantio através de processamento de imagens capturadas com drones. -->
## Pré-requisitos

Você deverá cumprir os seguintes itens:

- Ter uma conta na IBM Cloud
- Ter uma conta no [GitHub](https://github.com/) ou criar uma nova;


## 1 - Criando uma toolchain
1 - Abra o portal da [IBM Cloud](https://cloud.ibm.com)<br>

2 - Faça o login em sua conta<br>
3 - No canto superior esquerdo, clique no menu de navegação e clique em devops.<br>
 <div align="center">
    <img width="750" src="assets/homecloud.PNG" />
    <p>Imagem 3: Start a Project</p>
</div>
4 - Na tela de criação de toolchain, clique em Create a Toolchain. <br>
 <div align="center">
    <img width="750" src="assets/toolchains.PNG" />
    <p>Imagem 3: Start a Project</p>
</div>
5 - Como podemos ver, podemos criar a nossa toolchain do zero, ou utilizar algum dos templates, como kubernetes e Cloud Foundry. Selecione Develop Cloud Foundry APP.
<div align="center">
    <img width="750" src="assets/create-toolchain.PNG" />
    <p>Imagem 3: Start a Project</p>
</div>
6 - Dê um nome a sua toolchain, selecione uma região e um resource group.
 <div align="center">
    <img width="750" src="assets/creation-1.PNG" />
    <p>Imagem 3: Start a Project</p>
</div>
7 - Em Git Repos and Issue Tracking, dê um nome ao seu repositorio.
 <div align="center">
    <img width="750" src="assets/git.PNG" />
    <p>Imagem 3: Start a Project</p>
</div>
8 - Clique em `Delivery Pipeline` , entao dê um nome para seu aplicativo.

9 - Em API Key, clique em Create, para gerar uma nova API, e espere os campos seguintes carregarem.
 <div align="center">
    <img width="750" src="assets/pipe.PNG" />
    <p>Imagem 3: Start a Project</p>
</div>
9 - Feito isso, no canto superior direito da tela, clique em Create. Você será redirecionado para o Dashboard da sua Toolchain. Nesta página, temos 4 ferramentas: Issues, Git, Delivery Pipeline e Eclipse.
O processo de deploy da sua aplicação já está sendo executado. Podemos visualiza - lo clicando na ferramenta Delivery Pipeline.<br>

O Delivery Pipeline automatiza o Continuous Deployment de um projeto. Nele, podemos criar nossa esteira com uma sequencia de estágios e rodar tarefas como builds, testes e deployments. Neste exemplo, nosso pipeline possui apenas 2 tarefas: Build e Deploy.
10 - Para visualizar a aplicação que acabamos de criar, aguarde até que apareça `Stage Passed` em Deply, então, clique em View Console, onde irá te redirecionar para o dashboard da aplicação no Cloud Foundry.<br>
11 - Clique em Visit App URL.
<br>
<br>
<br>




## 2 - Alterando sua aplicação
<!-- Primeiramente, você deverá criar um novo repositório no GitHub. Abra sua conta no GitHub e clique em `Start Project`. Dê um nome para seu repositório e selecione a opção `Private`, para evitar que sua solução seja copiada. Por fim, clique em Create repository. -->
A toochain que criamos está integrada com o git, ou seja, quando uma alteração for realizada no repositório, o processo de deploy será executado automáticamente e a sua aplicação será atualizada.
Para testar este processo, volte para o dashboard da toolchain. <br> <br>
1 - primeiramente, vamos visualizar o Git que foi criado. Em code, clique em Git. Este é um Git próprio da IBM Cloud que é criado automáticamente com a nossa toolchain. Abrindo o arquivo manifest.yml, podemos ver as configurações necessárias para a nossa aplicação no Cloud Foundry.
<br><br>
2 - Agora, vamos editar nosso codigo. Para isso, nossa toolchain conta com o Eclipse orion Web IDE, que permite alterar os códigos sem precisar de uma IDE Local. Abra esta ferramenta. <br>

3 - Abra a pasta public, depois, abra o arquivo index.html. Altere onde está escrito Hello World para uma frase de sua preferência. <br>
4 - No canto superior esquerdo, clique em File > Save.<br>
5 - Agora, precisamos validar nossa alteração no repositório para que a aplicação seja atualizada. Na aba a esquerda, clique no segundo icone. Ao carregar, podemos ver que a alteração já foi reconhecida, então, basta digitarmos uma mensagem e clicarmos em commit.<br>
6 - Em outgoing, poderemos ver a alteração realizada. Clique em push e aguarde o processo ser sucedido.<br>
7 - Feito isso, podemos fechar o editor e voltar para nossa toolchain. Clicando novmaente no Delivery Pipeline, podemos ver os processos em execução novamente. Ao fim das tarefas, abra novamente a aplicação e veja o resultado da alteração.

CONTINUA
 <div align="center">
    <img width="750" src="assets/main-git.PNG" />
    <p>Imagem 3: Start a Project</p>
</div>
<div align="center">
    <img width="750" src="assets/creating-git.PNG" />
    <p>Imagem 4: Criação do repositório</p>
</div>
Agora, você deverá importar o código deste repositório para o seu. Para isso, clique em Import Code e cole a URL do repositório do desafio 9. Clique em Begin Import e aguarde o processo ser concluído. Quando concluído, volte para seu repositório e veja seu código.

<div align="center">
    <img width="750" src="assets/new-repo.PNG" />
    <p>Imagem 5: Novo repositório do gitHub</p>
</div>
<div align="center">
    <img width="750" src="assets/import.PNG" />
    <p>Imagem 6: Criação do repositório</p>
</div>

## 3 - Entendendo o Delivery Pipeline
O Openshift é uma plataforma Open Source desenvolvida pela Red Hat utilizada para a orquestração de containers baseada em Kubernetes. Em outras palavras,é uma plataforma que te permite fazer o deploy de suas imagens sem se preocupar com infraestrutura. Atualmente, esta ferramenta também está presente na IBM Cloud.

Para este desafio, será necessário subir sua página  no OpenShift na IBM Cloud. Para isso,abra o portal da IBM Cloud e troque sua conta para 1960796 - IBM PoC - Maratona Behind the Code.
<div align="center">
    <img width="750" src="assets/novoprint.jpeg" />
    <p>Imagem 7: Selecionando a conta</p>
</div>

Após selecionada, o dashboard será atualizado, e o recurso "Cluster de Kubernetes" irá aparecer. Clique em `Cluster de Kuernetes` e então, selecione o `d9`.
 <div align="center">
    <img width="750" src="assets/nova-conta.PNG" />
    <p>Imagem 8: Dashboard atualizado. </p>
</div>

 <div align="center">
    <img width="750" src="assets/clusters-do-kubernetes.PNG" />
    <p>Imagem 9: OpenShift d9</p>
</div>


Você será direcionado para o painel do OpenShift na IBM Cloud. Nesta tela você pode obter algumas informações sobre seu cluster. Para prosseguir o processo, clique em `Console da Web do OpenShift` para ser direcionado ao Web Console do OpenShift.
Você também pode abrir o console pelo seguinte link: https://red.ht/desafiofinal
 <div align="center">
    <img width="750" src="assets/dash.PNG" />
    <p>Imagem 10: Painel do OpenShift na IBM Cloud</p>
</div>

 <div align="center">
    <img width="750" src="assets/main-openshift.PNG" />
    <p>Imagem 11: Console do OpenSift</p>
</div>

Agora, podemos um projeto. Clique em Create Project.  Escolha um nome de sua preferência para o projeto e clique em Create

 <div align="center">
    <img width="750" src="assets/create_project.PNG" />
    <p>Imagem 12: Criação do projeto</p>
</div>

 <div align="center">
    <img width="750" src="assets/overview1.PNG" />
    <p>Imagem 13: Overview do projeto</p>
</div>

Na página de Overview, clique em Browse Catalog para continuar o deploy da aplicação. Você será direcionado para um catalogo. Procure pela opção "Python" (apenas Python) e selecione esta opção.

 <div align="center">
    <img width="750" src="assets/python.PNG" />
    <p>Imagem 14: Selecionando o modelo Python</p>
</div>

Quando selecionada, clique em next na etapa de `Information`. Em `Configuration` dê o nome da sua aplicação. `Este nome deverá ser seu id (OBS: Seu novo ID)`. Em Git Repository, coloque a URL do seu repositório criado após dar o Fork neste repositório. IMPORTANTE: Antes de clicar em next, clique em `Advanced Options`. 

<div align="center">
    <img width="750" src="assets/configuration.PNG" />
    <p>Imagem 15: Nomeando a aplicação</p>
</div>

<div align="center">
    <img width="750" src="assets/advanced_options.PNG" />
    <p>Imagem 16: Advanced Options</p>
</div>

Em Advanced Options, clique em `Create New Secret` e coloque seu usuário e senha do github. O Secret basicamente serve para guardar informações confidênciais em seu container.  Dê um nome ao seu secret e clique em create. 

<div align="center">
    <img width="750" src="assets/new-secret.PNG" />
    <p>Imagem 17: Criando um secret</p>
</div>

Para finalizar o processo, clique em Create. Após criado, clique novamente em Overview e procure pela aplicação que você criou. Espere até que fique azul ao lado de `pod`. Quando isso acontecer, clique na URL ao lado do nome da aplicação e você será direcionado para a página onde terá instruções sobre as próximas etapas necessárias.

<div align="center">
    <img width="750" src="assets/overview2.PNG" />
    <p>Imagem 18: Overview 2</p>
</div>


## 6 - Deletar o projeto
**OBS: Esta etapa deve ser seguida apenas se você quiser deletar e criar novamente seu projeto.** 
Caso tenha cometido algum erro e deseje refazer seu deploy, delete seu projeto e crie novamente o projeto e a aplicação. Para deletar seu projeto, clique no logo no canto superior esquerdo do seu console, selecione os três pontos ao lado do projeto que deseja deletar e clique em `Delete Project`. Digite o nome do projeto na caixa de diálogo e confirme, e ele será marcado para ser deletado. Após isso, basta seguir novamente o processo de criação de projeto.
## Material de apoio
- [Creating a Red Hat OpenShift on IBM Cloud cluster](https://cloud.ibm.com/docs/openshift?topic=openshift-openshift_tutorial)
- [Watson IOT Plataform - Python](https://ibm-watson-iot.github.io/iot-python/application/)
-  [Keras](https://ibm-watson-iot.github.io/iot-python/application/)
-  [Tensor Flow](https://www.tensorflow.org/guide/)
## Troubleshooting

1. O Console da Web do OpenShift não abriu ao clicar na opção? 

    Resposta: **Abra pelo seguinte link: https://red.ht/desafiofinal**

    <br>
2. Errei ao criar minha aplicação, o que devo fazer?
    Resposta: **Neste caso, [delete seu projeto](#6---deletar-o-projeto) e crie um novamente.**



## License

Copyright 2019 Maratona Behind the Code

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       http://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.
