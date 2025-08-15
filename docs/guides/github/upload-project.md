# Upload project to GitHub 🚀

Passo a passo para enviar o projeto para o GitHub.

## 1. Inicializar o Repositório Git Local

Primeiro, navegue até o diretório do seu projeto e inicialize um repositório Git. Isso só precisa ser feito uma vez.

```bash
    # Navegue até o diretório do seu projeto
    cd /Projects/GitHub/course-containers/

    # Inicializa um novo repositório Git
    git init

    # Renomeia a branch principal para "main" (uma prática comum hoje em dia)
    git branch -M main
```

## 2. Adicionar um commit inicial

```bash
    # Adiciona todos os arquivos no diretório atual ao stage
    git add .

    # Cria um commit com uma mensagem descritiva
    git commit -m "Commit inicial"
```

## 3. Criar um Repositório no GitHub

1. Vá para github.com e faça login.
2. Clique no ícone de + no canto superior direito e selecione New repository.
3. Dê um nome ao seu repositório (por exemplo, course-containers).
4. Importante: Deixe desmarcada a opção "Initialize this repository with a README", pois você já tem seus próprios arquivos.
5. Clique em Create repository.

## 4. Conectar e Enviar para o GitHub

Na página seguinte, o GitHub mostrará a URL do seu novo repositório. Você usará essa URL para conectar seu repositório local ao remoto.

```bash
    # Adiciona o repositório remoto do GitHub ao seu projeto local
    # Substitua a URL abaixo pela URL do SEU repositório
    git remote add origin https://github.com/SEU-USUARIO/SEU-REPOSITORIO.git

    # Envia (push) seus commits para o repositório "origin" na branch "main"
    # A flag -u configura o rastreamento para futuros pushes
    git push -u origin main
```

Depois de executar esses comandos, seus arquivos estarão no GitHub! 👍

Para futuras alterações, você só precisará usar **git add**, **git commit** e **git push**.
