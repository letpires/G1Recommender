# G1Recommender

Base de dados - https://drive.google.com/file/d/13rvnyK5PJADJQgYe-VbdXb7PpLPj7lPr/view


Seu desafio é desenvolver esse modelo de sistema de recomendação e realizar o deploy dele utilizando as técnicas aprendidas no curso. Nesse cenário, surge o desafio de fornecer recomendações personalizadas para cada usuário com base nos dados de notícias do G1, predizendo qual será a próxima notícia que ele vai ler. Alguns pontos importantes devem ser considerados:

✅ Como lidar com o cold-start? Usuários ou itens com poucas informações devem ser tratados de forma diferenciada em relação a perfis mais completos?

✅ O conceito de recência é essencial para garantir que as recomendações de notícias sejam relevantes e oportunas.

Seu projeto deve conter os seguintes passos. Não se esqueça de gravar um vídeo para explicar todo o projeto e a disponibilização do repositório do GitHub.

- Treinamento do modelo.
- Salvamento do modelo.
- Criação de uma API para previsões.
- Empacotamento com Docker.
- Testes e validação da API.
- Deploy em ambiente produtivo: API local ou nuvem (a nuvem é opcional).

🔴 Caso tenha acesso a algum serviço de nuvem (AWS, GCP), faça o deploy do container em um serviço como AWS ECS ou Google Cloud Run.



## Conjunto de treino

O conjunto de treino está disponibilizado em diferentes pastas, cada uma contendo informação complementar. Os arquivos treino_parte_X.csv, em que X é um valor de 1 até 6, consistem das colunas:

- userId: id do usuário.
- userType: usuário logado ou anônimo.
- HistorySize: quantidade de notícias lidas pelo usuário.
- history: lista de notícias visitadas pelo usuário.
- TimestampHistory: momento em que o usuário visitou a página.
- timeOnPageHistory: quantidade de ms em que o usuário ficou na página.
- numberOfClicksHistory: quantidade de clicks na matéria.
- scrollPercentageHistory: quanto o usuário visualizou da matéria.
- pageVisitsCountHistory: quantidade de vezes que o usuário visitou a matéria.

Além desses arquivos, a pasta de treino contém uma subpasta denominada de itens. Ela contém a seguinte informação:

- Page: id da matéria. Esse é o mesmo id que aparece na coluna history de antes.
- Url: url da matéria.
- Issued: data em que a matéria foi criada.
- Modified: última data em que a matéria foi modificada.
- Title: título da matéria.
- Body: corpo da matéria.
- Caption: subtítulo da matéria.

Este conjunto de treino consiste em dados de usuários reais da Globoplay. Eles foram coletados até uma data limite T (a maior data em todo o conjunto TimestampHistory).

## Conjunto de Validação
Capturando informações de um período posterior ao treino, ou seja, não existe sobreposição temporal com o treino, o conjunto de validação consiste em:

- userId: id do usuário.
- userType: usuário logado ou anônimo.
- history: lista de páginas que devem ser recomendadas ao usuário.


O seu objetivo é gerar um ranking para a coluna history. Ou seja: quando um usuário loga, é necessário prever quais serão os próximos acessos dele. Observe que o mesmo userId está tanto na validação quanto no treino.




