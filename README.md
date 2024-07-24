ins# API PARA CADASTRO E PROGRAMAÇÃO DE VIAGENS

API criada com o intuíto de ser consumida por um front-end para fazer o cadastro de viagens, convite de amigos, organização de passeios e links importantes.Irei separar em 4 tópicos que conterão seus sub-tópicos com as chamadas da API.

## VIAGENS
### Criação de viagem:

METHOD: POST.

URL: localhost:8080/trips

BODY:
{
  "destination": "Maragogi - AL",
  "starts_at": "2024-08-01T00:00:00.0000",
  "ends_at": "2024-05-15T21:51:54.7342",
  "emails_to_invite": [
		"email convidado 1",
		"email convidado 2"
	],
  "owner_name": "seu nome",
  "owner_email": "seu email"
}

RESPONSE: {
	"tripId": "ID da viagem"
}

![image](https://github.com/user-attachments/assets/1b4734ec-741b-4ba4-88b2-d5fe2f5ee2c4)

### Recuperar informações de viagem:

METHOD: GET.

URL: localhost:8080/trips/*id da viagem*

BODY: vazio

RESPONSE: {
	"id": "id da viagem",
	"destination": "Maragogi - AL",
	"startsAt": "2024-08-01T00:00:00",
	"endsAt": "2024-05-15T21:51:54.7342",
	"isConfirmed": true or false,
	"ownerName": "seu nome",
	"ownerEmail": "seu email"
}

![image](https://github.com/user-attachments/assets/f4bff24a-904f-4138-bf4a-b18ae2295273)

### Confirmar viagem:

METHOD: GET.

URL: localhost:8080/trips/*id da viagem*/confirm

BODY: vazio

RESPONSE:{
	"id": "id da viagem",
	"destination": "Maragogi - AL",
	"startsAt": "2024-08-01T00:00:00",
	"endsAt": "2024-05-15T21:51:54.7342",
	"isConfirmed": true or false,
	"ownerName": "seu nome",
	"ownerEmail": "seu email"
}

![image](https://github.com/user-attachments/assets/41a4b568-b345-4a4d-837a-a2b2076467b2)

### Atualizar viagem:

METHOD: PUT.

URL: localhost:8080/trips/*id da viagem*

BODY: {
  "destination": "Rio de Janeiro - RJ",
  "starts_at": "2024-06-25T21:51:54.7342",
  "ends_at": "2024-06-25T21:51:54.7342"
}

RESPONSE:{
	"id": "id da viagem",
	"destination": "Rio de Janeiro - RJ",
	"startsAt": "2024-06-25T21:51:54.7342",
	"endsAt": "2024-06-25T21:51:54.7342",
	"isConfirmed": true or false,
	"ownerName": "seu nome",
	"ownerEmail": "seu email"
}

![image](https://github.com/user-attachments/assets/5a47156c-d81a-44f9-8514-310a555364c4)

## PARTICIPANTES
### Convidar participantes:

METHOD: POST.

URL: localhost:8080/trips/*id da viagem*/invite

BODY: {
  "email": "email do convidado"
}

RESPONSE:{
	"id": "id do convidado"
}

![image](https://github.com/user-attachments/assets/f6962578-5534-43fd-9c88-6d87a38d901d)

### Confirmar participantes:

METHOD: POST.

URL: localhost:8080/participants/*id do participante*/confirm

BODY: {
  "name": "nome do participante"
}

RESPONSE:{
	"id": "cb61a25c-93d9-4faa-9d1f-d18bb116c7b2",
	"isConfirmed": true,
	"name": "Nome participante",
	"email": "email do participante",
	"trip": {
		"id": "a64e6311-9d47-43d3-a07c-c606958c9db1",
		"destination": "Maragogi - AL",
		"startsAt": "2024-08-01T00:00:00",
		"endsAt": "2024-05-15T21:51:54.7342",
		"isConfirmed": true,
		"ownerName": "seu nome",
		"ownerEmail": "seu email"
	}
}

![image](https://github.com/user-attachments/assets/a5f67f8a-d97b-447c-94fe-bd337bcaf8c4)

### Recuperar informações de participantes:

METHOD: GET.

URL: localhost:8080/trips/*id do participante*/participants

BODY: vazio

RESPONSE:[
	{
		"id": "id participante 1",
		"name": "nome participante 1",
		"email": "email participante 1",
		"isConfirmed": true or false
	},
	{
		"id": "id participante 2",
		"name": "nome participante 2",
		"email": "email participante 2",
		"isConfirmed": true or false
	},
	{
		"id": "id participante 3",
		"name": "nome participante 3",
		"email": "email participante 3",
		"isConfirmed": true or false
	}
]

![image](https://github.com/user-attachments/assets/97f90397-b7fa-4619-a624-74d90315f407)
