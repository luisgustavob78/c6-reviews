# Análise de Reviews - C6 Bank
Esse projeto visa o desenvolvimento de um case para coleta de dados de review do C6 Bank, disponíveis no Google Maps. O objetivo do case é utilizar alguns dos atuais modelos de inteligência artificial voltados para processamento de linguagem natural, os chamados "Large Language Models (LLMs)", para executar automaticamente algumas tarefas que seriam inviáveis de serem realizadas manualmente em volumes grandes de textos extensos. Nessas tarefas, a ideia é processar os reviews e identificar quais as principais queixas dos clientes e, a partir disso, mapear possíveis pontos de melhoria no serviço prestado. Para essa análise, serão utilizados modelos como:

* Identificação de idiomas;
* Classificação de sentimentos;
* GPT3.5-turbo: Classificação de tópicos.

### Desenvolvimento
A análise dos dados foi realizada de acordo com as seguintes etapas:

1. Coleta de dados do Google Maps usando a serpapi;
2. Filtro de reviews com rating <= 3;
3. Uso de um LLM para identificação de idioma para filtrar apenas reviews em português;
4. Uso de um LLM para filtrar os comentários com teor negativo;
5. Uso do GPT3.5-turbo para identificação dos tópicos que os clientes estão falando sobre.

Para a execução da etapa 5, foi pedido ao modelo GPT que classificasse os reviews em 5 categorias: Serviço ao cliente, Cobrança indevida, Experiência do usuário, Crédito e Fraude. Nesse contexto, tivemos a seguinte distribuição de classificações:
![](https://github.com/luisgustavob78/c6-reviews/blob/main/images/resultado_classificacao.png)

Para continuar o case, selecionamos Suporte ao cliente e cobrança indevida como os principais pontos a serem tratados. Usando o framework chamado "Opportunity Solution Tree", construímos o seguinte espaço de oportunidades e soluções possíveis para abordagem de cada uma das situações:
![](https://github.com/luisgustavob78/c6-reviews/blob/main/images/ost_customer_support.png)

![](https://github.com/luisgustavob78/c6-reviews/blob/main/images/ost_improper_billing.png)

### Reprodução
Para reproduzir o que foi desenvolvido aqui, o primeiro passo é clonar o repositório:

```git clone https://github.com/luisgustavob78/c6-reviews.git```

Para reproduzir o ambiente, basta instalar os requirements disponíves em requirements.txt

```pip install requirements.txt```

### Serviços de API
Tanto a serpapi para coleta de dados no Google Maps quanto a OpenAI para uso do GPT requerem a criação de conta em seus sites para consumo de suas respectivas APIs. Lá será possível criar as keys que darão acesso às APIs
