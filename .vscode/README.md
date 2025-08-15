# Padronizando o Ambiente com o Diretório `.vscode`

O diretório `.vscode` em nosso repositório serve para padronizar o ambiente de desenvolvimento para todos que utilizam o Visual Studio Code como editor.

Ao versionar essas configurações, garantimos que todos os colaboradores usem as mesmas extensões, configurações de formatação, e tarefas de depuração. Isso ajuda a manter a consistência do código e facilita a entrada de novos membros no projeto.

Abaixo estão os arquivos que você encontrará neste diretório e uma explicação sobre o que cada um faz.

---

## 1. `settings.json`

Este arquivo define configurações específicas do VS Code para este projeto. Elas sobrescrevem as configurações globais do seu editor, garantindo que todos sigam os mesmos padrões.

**Funcionalidade:**

- **Padroniza a formatação**: Garante que o código seja formatado ao salvar.
- **Configura o editor**: Define o formatador padrão (como o Prettier) e o comportamento de linters (como o ESLint).
- **Melhora a organização**: Oculta pastas e arquivos gerados (como `node_modules`) da árvore de arquivos do editor.

**Exemplo de configuração:**

```json
{
  "editor.formatOnSave": true,
  "editor.defaultFormatter": "esbenp.prettier-vscode",
  "editor.codeActionsOnSave": {
    "source.fixAll.eslint": "explicit"
  },
  "files.eol": "\n",
  "files.exclude": {
    "**/node_modules": true
  }
}
```

---

## 2. `extensions.json`

Este arquivo lista as extensões do VS Code recomendadas para o projeto. Ao abrir o repositório pela primeira vez, o VS Code irá notificá-lo para instalar essas extensões, facilitando a configuração do ambiente ideal.

**Funcionalidade:**

- **Garante as ferramentas certas**: Assegura que todos tenham as extensões necessárias para linting, formatação e depuração.
- **Facilita o onboarding**: Simplifica a configuração inicial para novos desenvolvedores.

**Exemplo de recomendações:**

```json
{
  "recommendations": [
    "dbaeumer.vscode-eslint",
    "esbenp.prettier-vscode",
    "github.vscode-pull-request-github"
  ]
}
```

---

## 3. `launch.json`

Este arquivo configura o depurador do VS Code. Com ele, você pode iniciar e depurar a aplicação com um único clique (pressionando `F5`), definindo pontos de interrupção, variáveis de ambiente e outros parâmetros.

**Funcionalidade:**

- **Simplifica a depuração**: Padroniza como a aplicação é iniciada para depuração.
- **Configurações múltiplas**: Permite criar diferentes perfis de depuração (ex: para o servidor e para os testes).

**Exemplo para um projeto Node.js:**

```json
{
  "version": "0.2.0",
  "configurations": [
    {
      "type": "node",
      "request": "launch",
      "name": "Debugar Aplicação Node.js",
      "program": "${workspaceFolder}/src/index.js",
      "skipFiles": ["<node_internals>/**"]
    }
  ]
}
```

---

## 4. `tasks.json`

Este arquivo permite automatizar tarefas comuns, como compilar o código, executar testes ou iniciar um servidor de desenvolvimento. Essas tarefas podem ser executadas através da paleta de comandos do VS Code (`Ctrl+Shift+P`).

**Funcionalidade:**

- **Automatiza scripts**: Integra ferramentas de linha de comando (como `npm` ou `dotnet`) diretamente no editor.
- **Suporte à depuração**: Pode ser usado para executar tarefas de build antes de uma sessão de depuração.

**Exemplo para executar scripts `npm`:**

```json
{
  "version": "2.0.0",
  "tasks": [
    {
      "label": "Executar testes",
      "type": "npm",
      "script": "test",
      "group": {
        "kind": "test",
        "isDefault": true
      }
    }
  ]
}
```
