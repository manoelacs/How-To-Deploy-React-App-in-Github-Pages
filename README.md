# Como fazer deploy de aplicações ReactJS no Github-Pages
Um gruia pra falicitar deploy dos seus tamplates feitos em ReactJS

## Procedimentos :

1- Primeiro criamos a aplicação em Reactjs my-app using create-react-app.

npm init react-app my-app

2- Instale o pacote GitHub Pages como dependência de desenvolvimento:

cd my-app
npm install gh-pages --save-dev

3- Adicione as seguintes propriedades ao arquivo package.json.

A primeira propriedade é adicionada no topo do arquivo o endereço da sua página será "http://{username}.github.io/{repo-name}" {username} é o seu usuário no GitHub,  e {repo-name} é o nome do seu repositório no Github :
(lembrando que pra esse link ficar disponível é preciso marcar a opçãp "Tamplate repository" no topo da seção Settings).

"homepage": "http://{username}.github.io/{repo-name}"

Segundo, ainda no package.json adicione as seguintes propriedade em scripts:

"scripts": {
//...
"predeploy": "npm run build" ,
"deploy": "gh-pages -d build"
}

Teremos o resultado igual da imagem a seguir:
![](https://res.cloudinary.com/practicaldev/image/fetch/s--MjMDNfNZ--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://thepracticaldev.s3.amazonaws.com/i/8kevraaawx8mi9ryx9lb.png)

4- Crie um repositório no Github então inicialize e adicione ele como um repositório remoto no seu git local. 
- Execute o comando a seguir: git remote add origin url_do_seu_repositório

5- Agora iremos fazer deploy para Github Pages. 
- Execute o comando a seguir: npm run deploy

![](https://res.cloudinary.com/practicaldev/image/fetch/s--nLcRus4E--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://thepracticaldev.s3.amazonaws.com/i/fsjvc2avaib2mskxqawa.png)

Este comando irá criar uma nova  branch chamada gh-pages ela irá hospedar seu app, para o endereço que foi adicionado em homepage no arquivo package.json , ou você pode encontrar esse link no seu repositório em Setting descer a página até encontrar a seção GitHub Pages :

![](https://res.cloudinary.com/practicaldev/image/fetch/s--bLvTaAKo--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://thepracticaldev.s3.amazonaws.com/i/573f5s4jgcn1a6caq65s.png)


6- commit and push no seu repositório Github. (Opcionalmente)

git add .
git commit -m "Sua mensagem"
git push origin master

Resumindo:

- [X] criamos um React App usando create-react-app
- [X] então instalamos o pacote gh-pages como depedência de desenvolvimento
- [X] no arquivo package.json nós adicinando algumas propriedade como homepage e editamos as propriedade de scripts,  adicionando predeploy and deploy
- [X] depois criamos um repsótio remoto ou adicionamos a um repositório já existente.
- [X] Executando npm run deploy ou yarn run deploy iremos gerar a build de produção  e fazer deploy no GitHub Pages.


Adaptado de [DEV -  autor: Ibrahim Ragab](https://dev.to/yuribenjamin/how-to-deploy-react-app-in-github-pages-2a1f)




