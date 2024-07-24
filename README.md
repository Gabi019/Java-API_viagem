# API PARA CADASTRO E PROGRAMAÇÃO DE VIAGENS

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
