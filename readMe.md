# Inicializar a aplicação

O presente repositório aplica a arquitetura de microsserviços de suporte à aplicação PhisioBuddy. Este sistema foi desenvolvido para a disciplina Projeto de Computação na Cloud no âmbito do Mestrado em Engenharia Informática do IPCA (24/25)


Para usar este sistema basta clonar o repositório e correr o docker-compose que vai buscar as imagens ao meu dockerhub. Já o repositório com as implementações dos serviços pode ser acedido aqui [aqui](https://github.com/orgs/app-physiobuddy/repositories)


Depois, para o message broker funcionar, é necessário:
- 1. Abrir o dashboard com user:admin e pass:password
- 2. Criar utilizador de autenticação com todos os passos _default_ e com user:pb e password:password (superuser=false)


>IMPORTANTE: Por vezes o exercise server e o entities server iniciam antes da base de dados estar pronta e a inicialização da base de dados falha. Não consegui resolver este comportamento automáticamente, mas se isso acontecer basta dar um restart no respetivo server container.

Na coleção do postman tem a _flow_ do processo de negócio. As bases de dados estão vazias, pelo que será possivel correr cada um dos _endpoints_ da coleção sem fazer nenhuma alteração.

A cache está implementada no _endpoint_ 10.2.  Os dados da cache expiram após 20 segundos de serem guardados.

O serviço de _upload_ está no _endpoint_ 10Versao2. A coleção do postman não mantem o vídeo, por isso será necessário incluir um vídeo em body - form-data - video
Nota: se testar mais que uma vez, deve mudar o nome do exercíco.