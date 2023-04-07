<h1 align="center">
  <br>
  <a href="https://github.com/context-labs/autodoc"><img src="https://raw.githubusercontent.com/context-labs/autodoc/master/assets/autodoc.png" alt="Markdownify" width="200" style="border-radius:8px;"></a>
  <br>
Autodoc
  <br>
</h1>
<h4 align="center">⚡ Conjunto de ferramentas para gerar automaticamente documentação de base de código usando LLMs ⚡</h4>
<p align="center">
<a href="https://opensource.org/licenses/MIT">
	  <img alt="Twitter URL" src="https://img.shields.io/badge/License-MIT-yellow.svg">
  </a>
	<a href="https://www.npmjs.com/package/@context-labs/autodoc">
	  <img alt="NPM Package" src="https://badge.fury.io/js/@context-labs%2Fautodoc.svg">
  </a>
  <a href="https://twitter.com/autodoc_">
	  <img alt="Twitter URL" src="https://img.shields.io/twitter/url?label=Follow%20%40autodoc_&style=social&url=https%3A%2F%2Ftwitter.com%2Fautodoc_">
	  <a href="https://discord.com/invite/zpFEXXWSNg">
	  <img alt="Discord Server" src="https://dcbadge.vercel.app/api/server/zpFEXXWSNg?compact=true&style=flat">
  </a>
</p>
<p align="center">
  <a href="#what-is-this">O que é isso?</a> •
  <a href="#get-started">Comece</a> •
  <a href="#community">Comunidade</a> •
  <a href="#contributing">Contribua</a>
</p>

### **O que é isso?**

Autodoc é um conjunto de ferramentas **experimental** para gerar automaticamente documentação de base de código para repositórios git usando Modelos de Linguagem de Grande Escala, como **[GPT-4](https://openai.com/research/gpt-4)** ou **[Alpaca](https://github.com/ggerganov/llama.cpp)**. O Autodoc pode ser **[instalado](https://chat.openai.com/chat?model=gpt-4#get-started)** em seu repositório em cerca de 5 minutos. Ele indexa sua base de código através de uma travessia em profundidade de todos os conteúdos do repositório e chama um LLM para escrever documentação para cada arquivo e pasta. Esses documentos podem ser combinados para descrever os diferentes componentes do seu sistema e como eles trabalham juntos.

A documentação gerada vive em sua base de código e acompanha onde seu código viaja. Os desenvolvedores que baixam seu código podem usar o comando **`doc`** para fazer perguntas sobre sua base de código e obter respostas altamente específicas com links de referência de volta aos arquivos de código.

No futuro próximo, a documentação será reindexada como parte do seu pipeline de CI, para que esteja sempre atualizada. Se você estiver interessado em trabalhar contribuindo para este trabalho, veja **[esta issue](https://github.com/context-labs/autodoc/issues/7)**.

### **Status**

Autodoc está nos estágios iniciais de desenvolvimento. Ele é funcional, mas não está pronto para

uso em produção. As coisas podem quebrar ou não funcionar conforme o esperado. Se você estiver interessado em trabalhar no framework central do Autodoc, consulte **[contribuindo](https://chat.openai.com/chat?model=gpt-4#contributing)**. Adoraríamos contar com sua ajuda!

### **Perguntas frequentes**

**Pergunta:** Não estou obtendo boas respostas. Como posso melhorar a qualidade das respostas?

**Resposta:** Autodoc está nos estágios iniciais de desenvolvimento. Como tal, a qualidade das respostas pode variar amplamente com base no tipo de projeto que você está indexando e em como as perguntas são formuladas. Algumas dicas para escrever uma boa consulta:

1. Seja específico com suas perguntas. Faça coisas como "Quais são os diferentes componentes de autorização neste sistema?" em vez de "explicar autenticação". Isso ajudará o Autodoc a selecionar o contexto certo para obter a melhor resposta para sua pergunta.
2. Use GPT-4. O GPT-4 é substancialmente melhor em entender código em comparação com o GPT-3.5, e esse entendimento se traduz em escrever uma boa documentação também. Se você não tiver acesso, inscreva-se **[aqui](https://openai.com/waitlist/gpt-4-api)**.

### **Exemplos**

Abaixo estão alguns exemplos de como o Autodoc pode ser usado.

1. **[Autodoc](https://github.com/context-labs/autodoc)** - Este repositório contém documentação para si mesmo, gerada pelo Autodoc. Ele vive na pasta **`.autodoc`**. Siga as instruções **[aqui](https://chat.openai.com/chat?model=gpt-4#querying)** para aprender como consultá-lo.
2. **[TolyGPT.com](https://tolygpt.com/)** - TolyGPT é um chatbot Autodoc treinado na base de código **[Solana validator](https://github.com/solana-labs/solana)** e implantado na web para fácil acesso. No futuro próximo, o Autodoc suportará uma versão web além da ferramenta CLI existente.

## **Comece**

### Requisitos

Autodoc requer Node v18.0.0 ou superior. Recomenda-se v19.0.0 ou superior. Certifique-se de que você está executando a versão adequada:

```
bashCopy code
$ node -v

```

Exemplo de saída:

```
bashCopy code
v19.8.1

```

Instale a ferramenta CLI Autodoc como um módulo global NPM:

```
bashCopy code
$ npm install -g @context-labs/autodoc

```

Este comando instala a ferramenta CLI Autodoc que permitirá criar e consultar índices Autodoc.

Execute **`doc`** para ver os comandos disponíveis.

### **Consultando**

Usaremos o repositório Autodoc como exemplo para demonstrar como funciona a consulta no Autodoc.

Clone Autodoc e mude o diretório para começar:

```
bashCopy code
$ git clone https://github.com/context-labs/autodoc.git
$ cd autodoc

```

No momento, Autodoc suporta apenas OpenAI. Certifique-se de ter sua chave API OpenAI exportada em sua sessão atual:

```
bashCopy code
$ export OPENAI_API_KEY=<SUA_CHAVE_AQUI>

```

Para iniciar a CLI de consulta Autodoc, execute:

```
bashCopy code
$ doc q

```

Se esta for a primeira vez que você executa **`doc q`**, verá uma tela que solicita que você selecione quais modelos GPT você tem acesso. Selecione o que for apropriado para seu nível de acesso. Se você não tiver certeza, selecione a primeira opção:

<img src="https://raw.githubusercontent.com/context-labs/autodoc/master/assets/select-models.png" alt="Markdownify" width="60%" style="border-radius:24px;">

Agora você está pronto para consultar a documentação do repositório Autodoc:

<img src="https://raw.githubusercontent.com/context-labs/autodoc/master/assets/query.gif" alt="Markdownify" width="60%" style="border-radius:24px;">

Esta é a experiência básica de consulta. É muito básico no momento, com muito espaço para melhorias. Se você estiver interessado em melhorar a experiência de consulta CLI Autodoc, confira **[este problema](https://github.com/context-labs/autodoc/issues/11)**.

### **Indexando**

Siga as etapas abaixo para gerar documentação para seu próprio repositório usando Autodoc.

Mude o diretório para a raiz do seu projeto:

```
bashCopy code
cd $PROJECT_ROOT

```

Certifique-se de que sua chave API OpenAI está disponível na sessão atual:

```
bashCopy code
$ export OPENAI_API_KEY=<SUA_CHAVE_AQUI>

```

Execute o comando **`init`**:

```
csharpCopy code
doc init

```

Você será solicitado a inserir o nome do seu projeto, a URL do GitHub e selecionar quais modelos GPT você tem acesso. Se você não tiver certeza de quais modelos tem acesso, selecione a primeira opção. Este comando irá gerar um arquivo **`autodoc.config.json`** na raiz do seu projeto para armazenar os valores. Este arquivo deve ser adicionado ao git.

**Nota:** Não pule a inserção desses valores ou a indexação pode não funcionar.

**Configuração de Prompt:** Você encontrará instruções de prompt especificadas em **`prompts.ts`**, com alguns trechos personalizáveis no **`autodoc.config.json`**. Os prompts atuais são focados no desenvolvedor e supõem que seu repositório é focado em código. Teremos mais modelos de referência no futuro.

Execute o comando **`index`**:

```
bashCopy code
doc index

```

Você deve ver uma tela como esta:

<img src="https://raw.githubusercontent.com/context-labs/autodoc/master/assets/index-estimate.png" alt="Markdownify" width="60%" style="border-radius:24px;">

Esta tela estima o custo de indexar seu repositório. Você também pode acessar esta tela através do comando **`doc estimate`**. Se você já indexou uma vez, o **`doc index`** só reindexará os arquivos que foram alterados na segunda vez.

Para cada arquivo em seu projeto, o Autodoc calcula o número de tokens no arquivo com base no conteúdo do arquivo. Quanto mais linhas de código, maior o número de tokens. Usando esse número, ele determina qual modelo usará por arquivo, sempre escolhendo o modelo mais barato cujo comprimento de contexto suporte o número de tokens no arquivo. Se você estiver interessado em ajudar a tornar a seleção de modelo configurável no Autodoc, confira [este problema](**[https://github.com/context-labs/autodoc/issues/9](https://github.com/context-labs/autodoc/issues/9)).**

).

**Nota:** Essa estratégia ingênua de seleção de modelo significa que arquivos com menos de ~4000 tokens serão documentados usando GPT-3.5, o que resultará em documentação menos precisa. **Recomendamos o uso de GPT-4 8K no mínimo.** A indexação com GPT-4 resulta em uma saída significativamente melhor. Você pode se inscrever para acessar **[aqui](https://openai.com/waitlist/gpt-4-api)**.

Para projetos grandes, o custo pode ser de várias centenas de dólares. Veja os preços da OpenAI **[aqui](https://openai.com/pricing)**.

Em um futuro próximo, ofereceremos suporte a modelos auto-hospedados, como **[Llama](https://github.com/facebookresearch/llama)** e **[Alpaca](https://github.com/tatsu-lab/stanford_alpaca)**. Leia **[este problema](https://github.com/context-labs/autodoc/issues/8)** se você estiver interessado em contribuir para este trabalho.

Quando o repositório terminar de ser indexado, você verá uma tela como esta:

<img src="https://raw.githubusercontent.com/context-labs/autodoc/master/assets/index-finished.png" alt="Markdownify" width="60%" style="border-radius:24px;">

Agora você pode consultar seu aplicativo usando as etapas descritas em **[consultando](https://chat.openai.com/chat?model=gpt-4#querying)**.

## **Comunidade**

Há um pequeno grupo de nós que estão trabalhando em tempo integral no Autodoc. Junte-se a nós no **[Discord](https://discord.gg/zpFEXXWSNg)** ou siga-nos no **[Twitter](https://twitter.com/autodoc_)** para atualizações. Estaremos postando regularmente e continuando a melhorar o aplicativo Autodoc. Quer contribuir? Leia abaixo.

## **Contribuindo**

Como um projeto de código aberto em um campo em rápido desenvolvimento, estamos extremamente abertos a contribuições, seja na forma de um novo recurso, infraestrutura aprimorada ou melhor documentação.

Para obter informações detalhadas sobre como contribuir, consulte **[aqui](https://chat.openai.com/.github/CONTRIBUTING.md)**.
