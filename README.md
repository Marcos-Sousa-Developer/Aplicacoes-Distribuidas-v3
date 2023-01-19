<p align="center">
    <img src="https://www.freepnglogos.com/uploads/server-png/server-icon-download-icons-17.png" alt="Logo" width="80" height="80">
</p>

# <h1 align="center">Gestor de bloqueios a recursos para leituras e escritas</h1>
<h4 align="center">Projeto para a cadeira de Aplicações Distribuídas (Parte3) (2021/2022)</h4>

<hr>

# Objetivo
Objetivo geral do presente projeto será concretizar um serviço Web para gerir um sistema simplificado de classificação de músicas de utilizadores. A implementação vai utilizar o estilo arquitetural REST e uma base de dados relacional acessível pela linguagem SQL. <br>
Para este efeito, serão utilizados a framework de desenvolvimento Web Flask e o motor de base de dados SQL sqlite no servidor. O programa cliente utilizará o módulo requests para implementar a interação cliente/servidor baseada em HTTP.

<hr>

# Passos

## 1ºPasso: Autenticação 

### Para ter acesso à API REST do Spotify é preciso seguir alguns passos de autenticação e autorização

1. Entrar em https://developer.spotify.com/dashboard/
2. Fazer o login ou criar uma nova conta.
3. Registar uma applicação. Para isso basta definir o nome da aplicação e descrever
brevemente o objetivo da aplicação.
4. Copiar o Client ID e o Client Secret
5. Ler atentamente a documentação da API Web do Spotify.
6. Executar alguns testes simples na Spotify Web API Console.
7. Após preencher os campos do pedido, é preciso gerar um token OAuth para estar
autorizado a executar o comando.
8. Executar alguns testes simples com o comando curl, como no exemplo a seguir.
Pode-se substituir o campo nome_artista pelo nome do artista que pretende buscar na
plataforma, assim como deve-se substituir o campo meu_OAuthToken pelo token
obtido no passo anterior: 

```bash
curl -X "GET"
"https://api.spotify.com/v1/search?q=nome_artista&type=artist" -H
"Accept: application/json" -H "Content-Type: application/json" -H
"Authorization: Bearer meu_OAuthToken"
``` 
9. Para o Projeto 3, é suficiente copiar manualmente o token obtido no Passo 7 para uma variável no código do programa servidor. Este token possui uma duração limitada, o implica que este passo possa ter de ser refeito algumas vezes durante o desenvolvimento do projeto.

## 2ºPasso: Conexão

#### **Run these two on different terminals** 

```bash
python3 cliente.py 
```
```bash
python3 python3 server.py
```
<hr> 

# Instruções (In the client.py terminal)

## Comando CREATE

```bash
CREATE UTILIZADOR <nome> <senha> 
```
```bash
CREATE ARTISTA <id_spotify> 
```
```bash
CREATE MUSICA <id_spotify> 
```
```bash
CREATE <id_user> <id_musica> <avaliacao>
```

## Comando READ ou DELETE

```bash
READ|DELETE UTILIZADOR <id_user>
```
```bash
READ|DELETE ARTISTA <id_artista>
```
```bash
READ|DELETE MUSICA <id_musica>
```
```bash
READ|DELETE ALL < UTILIZADORES | ARTISTAS | MUSICAS>
```
```bash
READ|DELETE ALL MUSICAS_A <id_artista>
```
```bash
READ|DELETE ALL MUSICAS_U <id_user>
```
```bash
READ|DELETE ALL MUSICAS <avaliacao>
```

## Comando UPDATE

```bash
UPDATE MUSICA <id_musica> <avaliacao> <id_user>
```
```bash
UPDATE UTILIZADOR <id_user> <password>
```

