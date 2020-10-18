# tic-tac-toe-rep

## Descrição do projeto
Hackenge da cadeira de Engenharia de Software que objetiva a construção de um projeto de backend baseado numa API Restful que funcione para um projeto de Jogo da Velha. A estrutura escolhida foi baseada num modelo de CRUD clássico que pode ser usado para as mais diversas aplicações, portanto, é altamente adaptável e adequado à situação.

## Resources

### /game-board

#### ```GET /game-board```
Método utilizado para obter todos os tabuleiros disponíveis no sistema.
Exemplo de objeto enviado:```
{}```
Exemplo de resposta: ``` 
{
	{
		"board_id": "1245",
		"members" : [],
		"sequence" : [Null,Null,Null,Null,Null,Null,Null,Null,Null]
	}
}``` 
Exceção: Sem exceções

#### ``` PUT /game-board``` 
Método utilizado para a criação de um tabuleiro.
Exemplo do objeto enviado:``` 
{
  "board_id": "4321",
  "user_id" : "viniciusdarosa"
}``` 
Exemplo de resposta:``` 
{
  "board_id":4321,
  "action_status": "Sucess"
}``` 
Exceção: user_id inválido

#### ``` PATCH /game-board``` 
Método de múltipla utilidade, que pode alterar o tabuleiro ou reiniciar o jogo caso o mesmo tenha finalizado.
Exemplo do objeto enviado: ```
{
	"board_id": "1245",
	"goal" : "restart",
  "position": Null
}```
Exemplo de resposta:```
{
	"board_id": "1245",
	"members" : ["viniciusdarosa","examplemember"],
	"sequence" : [Null,Null,Null,Null,Null,Null,Null,Null,Null]
}```
Exceção : Posição inválida para o goal "move" ou board_id inválido

#### ``` DELETE /game-board```
Método utilizado para deletar o tabuleiro, que só pode ser chamado pelo criador do mesmo.
Exemplo do objeto enviado:```
{
	"board_id": "1245",
  "user_id": "viniciusdarosa"
}```
Exemplo da resposta:```
{
	"board_id": "1245",
  "status" : Success
}```
Exceção : board_id inválido ou user_id inválido

### /user

#### ``` PUT /user``` 
Método utilizado para criar o usuário.
Exemplo do objeto enviado:```
{
  "user_id": "viniciusdarosa",
  "senha": "samplepassword"
}```
Exemplo da resposta:```
{
  "user_id": "viniciusdarosa",
  "Status: "Sucesss"
}``` 
Exceção: Sem exceções

#### ``` POST /user``` 
Método utilizado para fazer o usuário entrar ou sair do tabuleiro.
Exemplo do objeto enviado: ``` 
{
  "user_id": "viniciusdarosa",
  "board_id": "1245",
  "goal": "enter"
}```
Exemplo da resposta: ``` 
{
  "user_id": "viniciusdarosa",
  "board_id": "1245",
  "status": "Success"
}```
Exceção: board_id inválido

#### ``` DELETE /user ``` 
Deleta o usuário terminando a sessão.
Exemplo do objeto enviado: ``` 
{
  "user_id": "viniciusdarosa",
  "senha" : "samplepassword"
}```
Exemplo da resposta: ``` 
{
  "user_id": "viniciusdarosa",
  "status": "Success"
}```
Exceção: senha ou user_id inválidos







