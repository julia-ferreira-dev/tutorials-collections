# Meu tutorial baby steps versão TS 

## 1. Node.js e Yarn

Antes de começar, certifique-se de que o **Node.js** está instalado em seu sistema. O Node.js é necessário para gerenciar pacotes e dependências do projeto.

### Verificando a versão do Node.js
No terminal, execute o comando abaixo para verificar qual versão do Node.js está instalada:
```bash
node -v 
```
### Dúvida: Diferença entre Sintaxes de Comandos em Terminais 
Existem várias formas de verificar a versão de um software, como **Node.js**, porque essas variações de comandos são implementadas para facilitar a vida do usuário, proporcionando flexibilidade. Aqui está o motivo por trás disso:

### 1. **Padronização e convenções**:
Comandos como `--version` seguem uma convenção padrão em sistemas Unix (como Linux e macOS) e também em terminais de sistemas como Windows. Esse é o formato mais completo, e muitos programas adotam essa forma para fornecer informações sobre a versão. Da mesma forma, `-v` é uma forma abreviada que muitas ferramentas também adotam, tornando o comando mais rápido de digitar.

### 2. **Variação entre ferramentas**:
Diferentes ferramentas e linguagens implementam seus próprios "atalhos" para comandos comuns. No caso do **Node.js**, tanto `-v` quanto `--version` foram implementados para oferecer a mesma funcionalidade de maneira flexível, atendendo aos desenvolvedores que preferem versões mais curtas ou mais completas do comando.

### 3. **Compatibilidade**:
Alguns terminais ou sistemas mais antigos podem exigir uma sintaxe específica. Implementar mais de uma forma de verificar a versão ajuda a manter compatibilidade com diversos ambientes, tanto no Linux, Windows ou macOS.

### 4. **Convenção de uma ou duas barras**:
- **Uma barra (`-`)**: Usada normalmente para abreviações, como `-v`.
- **Duas barras (`--`)**: Usada para comandos completos e mais descritivos, como `--version`. Isso facilita a criação de ferramentas mais complexas que oferecem múltiplas opções de linha de comando.

### Instalando e usando o nvm

#### Linux/Mac:
1. Instale o **nvm** com o comando:
   ```bash
   curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.4/install.sh | bash
   ```
2. Após a instalação, recarregue o terminal:
   ```bash
   source ~/.bashrc
   ```

#### Windows:
No Windows, use a versão adaptada, chamada **nvm-windows**:
1. Baixe o instalador em: [nvm-windows releases](https://github.com/coreybutler/nvm-windows/releases).
2. Após a instalação, abra um novo terminal e use os mesmos comandos que no Linux/Mac.

### Comandos principais do nvm:
- **Instalar uma versão específica do Node.js**:
  ```bash
  nvm install 14.17.0
  ```

- **Listar as versões instaladas**:
  ```bash
  nvm ls
  ```

- **Alternar para uma versão específica**:
  ```bash
  nvm use 14.17.0
  ```

- **Definir uma versão padrão**:
  ```bash
  nvm alias default 14.17.0
  ```

Após garantir que a versão correta do Node.js está instalada, você pode continuar com a instalação do **Yarn**.

---

Essa adição garante que você tenha o controle sobre as versões do Node.js, permitindo trabalhar com múltiplos projetos que exigem versões diferentes sem complicações.

### Yarn

Depois de instalar o Node.js, você pode instalar o Yarn, que será usado para gerenciar as dependências do projeto.

```bash
npm install --global yarn
```

O Yarn funciona de forma semelhante ao npm, mas com algumas vantagens em relação à velocidade e controle de cache. Por enquanto, estamos utilizando o Yarn para testar algo novo.

### Dúvida: Diferenças entre npm e Yarn

- O `npm` é o gerenciador de pacotes padrão que vem com o Node.js, enquanto o `Yarn` é uma alternativa criada pelo Facebook.
- **Benefícios do Yarn** incluem:
  - Maior rapidez nas instalações.
  - Melhor gerenciamento de cache.
  - Controle mais detalhado das dependências.
  
**Referência Acadêmica**: Ambos os gerenciadores de pacotes podem ser comparados a sistemas de controle de bibliotecas que você já deve ter estudado na disciplina de Engenharia de Software.
Em **Engenharia de Software**, um sistema de controle de bibliotecas é um exemplo de aplicação projetada para gerenciar e automatizar as operações de uma biblioteca física ou digital. Ele facilita o controle sobre o acervo de livros, revistas, periódicos e outros materiais, além de gerenciar o empréstimo, a devolução e o cadastro de usuários. De forma semelhante, o **npm** (Node Package Manager) funciona como um sistema de controle de bibliotecas, mas no contexto de desenvolvimento de software. O npm gerencia e automatiza o controle de pacotes (bibliotecas de código), facilitando a instalação, atualização e remoção dessas dependências em projetos de **Node.js**. Assim como o sistema de controle de bibliotecas organiza e gerencia o acervo e suas transações, o npm organiza e mantém as dependências de um projeto, garantindo que as bibliotecas estejam sempre disponíveis e atualizadas.

Portanto, o **npm** age como uma "biblioteca digital" de pacotes, permitindo que desenvolvedores baixem, atualizem e compartilhem código de forma eficiente, semelhante ao modo como uma biblioteca tradicional gerencia seu acervo de materiais.

---

## 2. Inicializando o Projeto

Crie um arquivo `package.json` com o comando abaixo:

```bash
yarn init -y
```

Este comando cria um arquivo `package.json`, que armazena informações sobre o projeto e suas dependências. O `-y` é literalmente um 'yes' mas de forma reduzida, aceita automaticamente as configurações padrão.

### Dúvida: O que é um packge.json? 
- É um arquivo JSON que contém metadados sobre o projeto, como nome, versão, descrição e, principalmente, as dependências (pacotes) que o projeto utiliza. Ele serve como um manifesto para o gerenciador de pacotes (npm ou Yarn) e permite que outros desenvolvedores reproduzam o ambiente do projeto facilmente.

### Dúvida: O que é um JSON? 
- JSON é a abreviação de JavaScript Object Notation. É um formato de texto leve e de fácil leitura, amplamente utilizado para trocar dados entre sistemas. Imagine-o como uma forma organizada de armazenar informações, similar a um dicionário, mas em um formato que máquinas entendem facilmente.

### Dúvida: Criar manualmente ou via terminal o packge.json?
- Ambos os métodos são válidos. Criar manualmente oferece mais controle, mas o terminal agiliza o processo. A escolha depende das preferências do desenvolvedor e da complexidade do projeto.

---

## 3. Adicionando TypeScript ao Projeto

TypeScript será usado para facilitar o desenvolvimento com **tipagem estática** e melhorar a manutenção do código ao longo do tempo.

```bash
yarn add -D typescript
```

Aqui, o `-D` significa que o TypeScript será instalado como dependência de desenvolvimento.



### Dúvida: O que é tipagem estática?
- É um sistema de verificação de tipos que ocorre em tempo de compilação. Ou seja, o compilador verifica se as variáveis estão sendo usadas de acordo com o tipo declarado, ajudando a prevenir erros comuns em tempo de execução. No TypeScript, você declara o tipo de uma variável ao declará-la, por exemplo: ``let nome: string = "João";``

### Verificando a versão do TypeScript:

```bash
tsc --version
```

---

## 4. Adicionando o Express

O **Express** é um framework de servidor para Node.js. Ele será usado para lidar com as requisições HTTP de nossa aplicação.

```bash
yarn add express
```

### Dúvida: O que é um servidor?
 
- Um servidor é uma aplicação que escuta por requisições de clientes (navegadores, por exemplo) e responde a essas requisições com dados ou serviços.
  
  **Referência Acadêmica**: Este conceito está relacionado à disciplina de Redes de Computadores, onde você aprende sobre comunicação entre cliente-servidor e protocolos como HTTP.
  Explique usando uma didática semelhante a **Referência Acadêmica** anterior.
   
---

## 5. Criando a Estrutura do Projeto

Dentro da pasta do backend, crie uma pasta `src` para armazenar os arquivos TypeScript:

```bash
mkdir src
```
Você também verá a pasta `node_modules`, onde todas as dependências instaladas estão localizadas.

### Dúvida: o que é uma pasta src?
- É uma convenção comum em projetos de software para armazenar o código fonte. A sigla "src" vem de "source" (fonte). Separar o código fonte em uma pasta específica facilita a organização do projeto e a compreensão do fluxo do código.

### Dúvida: Clear code e convenções sobre pastas?
- Clear code se refere a código bem escrito, fácil de entender e manter.
- As convenções sobre pastas variam de projeto para projeto, mas algumas práticas comuns incluem:
src: Código fonte.
test: Testes.
public: Arquivos estáticos (HTML, CSS, imagens).
config: Arquivos de configuração.
node_modules: Dependências.

### Dúvida: o que é uma pasta node_modules?
- É a pasta onde o npm ou Yarn instalam as dependências do projeto. Cada dependência é um pacote de código que pode ser reutilizado em outros projetos.
  
---

## 6. Import e Export

```ts
import express from 'express';

const app = express();

app.listen(3333);
```

### Dúvida: Por que usar TypeScript se ele compila para JavaScript?

- O TypeScript oferece uma camada extra de segurança e produtividade, especialmente em projetos grandes e complexos. Além disso, ele permite utilizar recursos mais modernos do JavaScript de forma mais segura.
- **JavaScript já possui `import` e `export`** em suas versões mais recentes (ES6), mas o TypeScript oferece suporte a versões anteriores do JavaScript também.

### Conceito de "Feature"

- Uma **feature** é um recurso ou funcionalidade de uma linguagem. No caso do TypeScript, ele estende funcionalidades do JavaScript, como tipagem estática e interfaces.

  **Pergunta Acadêmica**: **TS é considerado uma linguagem de programação?**
  - O TypeScript é um **superset** do JavaScript, o que significa que ele é uma extensão do JavaScript e, portanto, compartilha muitos aspectos, mas não é uma linguagem completamente separada.

### Dúvida: O criador do node, criou o deno então o TS não seria considerado uma linguagem por isso?
- O Deno é um runtime para JavaScript e TypeScript que oferece uma alternativa ao Node.js. A existência do Deno não muda a natureza do TypeScript. Ele continua sendo um superconjunto do JavaScript e oferece os mesmos benefícios.

---

## 7. Compilação do TypeScript para JavaScript

O código TypeScript precisa ser compilado para JavaScript para rodar no Node.js. Você pode compilar o arquivo `src/index.ts` usando o comando:

```bash
yarn tsc src/index.ts
```

### Dúvida: O que é uma flag?

- Uma **flag** é um parâmetro adicional passado para comandos que alteram o comportamento de execução. No caso do erro acima, o TypeScript exige que você ative a flag `esModuleInterop` para permitir a importação de módulos exportados como `default`.

**Resolvendo o Erro:**

No arquivo `tsconfig.json`, adicione a seguinte configuração:

```json
{
  "compilerOptions": {
    "esModuleInterop": true
  }
}
```

Isso permitirá que você use a sintaxe `import express from 'express'` sem erros.

continua...
