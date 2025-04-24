# Revisão: Setup e Versionamento de Projeto JavaScript via CMD

Este material reúne,  o **passo a passo**, tudo que vimos até agora usando **cmd.exe** no Windows referente aos interesses de *criação de projeto **JS** e Versionamento com **Git***  . Ao final, há instruções para rodar seu código diretamente e breves alternativas.

---
# Sumário de atividades:

- Instalou/verificou Node.js
    
- Criou pasta, inicializou npm
    
- Estruturou `src`/`dist`, criou `index.js`
    
- Abriu no VS Code
    
- Versionou com Git, criou branch
    
- Commitou e enviou ao GitHub
    
- Aprendeu a rodar no cmd e alternativas rápidas.

--- 

# Atividades realizadas
## 1. Instalar e verificar Node.js + npm

1. **Verificar se já está instalado**  
   ```bat
   node -v    # ex.: v18.15.0
   npm -v     # ex.: 9.5.0

Pra que instaler o NOde.Js e NPM?
### 1.2 Por que instalar **Node.js** e **npm**?

1. **Executar JavaScript fora do navegador**  
   - Com o **Node.js** você roda scripts JS diretamente no seu computador (linha de comando), ideal para tarefas de automação, testes ou back-end simples.  
   - Exemplo:  
     ```bash
     node src/index.js
     ```

2. **Gerenciar dependências e pacotes**  
   - O **npm** (“Node Package Manager”) permite instalar, atualizar e remover bibliotecas de terceiros com um só comando:  
     ```bash
     npm install express
     ```  
   - Mantém suas dependências versionadas em `package.json`/`package-lock.json`.

3. **Scripts e automação de tarefas**  
   - No `package.json` você define atalhos (“scripts”) para compilar, testar, executar ou empacotar seu projeto:
     ```jsonc
     "scripts": {
       "build": "webpack --mode production",
       "start": "node src/index.js",
       "test": "jest"
     }
     ```
   - Depois é só usar:
     ```bash
     npm run build
     ```

4. **Ferramentas de desenvolvimento modernas**  
   - Bundlers (Webpack, Parcel, Vite), transpiladores (Babel), linters (ESLint), test runners (Jest), servidores de desenvolvimento (live-server), e muito mais rodam sobre Node.js.

5. **Criar servidores e APIs**  
   - Com frameworks como **Express** ou **Koa**, você pode montar um servidor HTTP completo em poucos minutos:
     ```js
     const express = require('express');
     const app = express();
     app.get('/', (req, res) => res.send('Olá, mundo!'));
     app.listen(3000);
     ```

---

> **Em resumo:**  
> - **Node.js** fornece o runtime JavaScript no desktop/servidor.  
> - **npm** é o ecossistema de pacotes e o sistema de scripts que agiliza seu fluxo de trabalho.

## 2. Criar pasta do projeto e iniciar npm

```
1. cd C:\Users\jmtec\Desktop # verificar em que diretório a pasta está sendo criada
2. `md RevisaoJs`         # cria a pasta
3. `cd RevisaoJs `        # entra nela
4. `npm init -y`          # gera package.json com valores padrão

* ***`npm init -y`** salta o assistente e usa defaults.
* ***Alternativa**: `npm init` sem `-y` para responder perguntas manualmente. - haverão perguntas no jason para a criação do projeto

```

## 3. Estruturar pastas e criar `index.js`

```
1. `md src dist`  # comando q cria a pasta
2. `type nul > src\index.js`  

* ***`type nul > …`** cria (ou zera) o arquivo vazio.
* ***Alternativa**: `npm init` sem `-y` para responder perguntas manualmente.
```

## 4. Abrir no VS Code
```
`code .` comando que abre o Vscode dentro do CMD

- **Abre** todo o projeto no VS Code.
    
 * ***Alternativa**:  Use `start .` para abrir no Explorer e depois clique em seu editor favorito.
```

## 5. Escrever um `console.log`

 # no arquivo do VsCode Chamado: **src/index.js**: escreva:

```
console.log("Olá, JavaScript!");
```

## 6. Inicializar Git e primeiro commit

```
git init                          # cria .git/
git add .                         # adiciona tudo ao staging
git commit -m "Inicializa projeto JavaScript"
```

## 7. Criar e usar branch de aprofundamento

>> A nova branch foi denominada aprofundamento1

```
git checkout -b aprofundamento1   # cria e muda para ela.
```


>> Após a criação da nova branch e de verificar através do `git branch` em que branch estamos trabalhando.  na nova branch os proximos passos são:
## 8. Commit na nova branch: aprofundamento1

```
git add . # informa os arquivos que serão enviados ao github
git commit -m "feat: adiciona log de saudação" # marca o titulo daquela atualização
```

## 9. Publicar branch no GitHub


```
git push -u origin aprofundamento1
```

* ***`-u`** vincula sua branch local à `origin/aprofundamento1` no remoto.

## 10. Como rodar seu código no CMD

```
node src\index.js #direto no cmd, executa a pasta index.js
```

```
"scripts": {
  "start": "node src/index.js" #via Script npm em package.json
}
```

```
npm start
```

```
node -e "console.log('Teste rápido'); # executa os comando do console 
```
