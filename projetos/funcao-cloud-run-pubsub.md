# Função no Cloud Run pela linha de comando

Neste laboratório, fiz o seguinte:

- configurei a região do Cloud Run para `us-east1`;
- criei a pasta `gcf_hello_world` no Cloud Shell;
- preparei o `package.json` e instalei as dependências com `npm install`;
- publiquei a mensagem `Cloud Function Gen2` no tópico Pub/Sub `cf-demo`;
- consultei os logs da função `nodejs-pubsub-function`.

Resultado: a função recebeu a mensagem do Pub/Sub e registrou `Hello, Cloud Function Gen2!` nos logs.
