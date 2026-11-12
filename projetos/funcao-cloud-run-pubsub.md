# Função no Cloud Run pela linha de comando

Neste laboratório, fiz o seguinte:

- configurei a região do Cloud Run para `us-east1`;
- criei a pasta `gcf_hello_world` no Cloud Shell;
- preparei o `package.json` e instalei as dependências com `npm install`;
- publiquei a mensagem `Cloud Function Gen2` no tópico Pub/Sub `cf-demo`;
- consultei os logs da função `nodejs-pubsub-function`.

Resultado: a função recebeu a mensagem do Pub/Sub e registrou `Hello, Cloud Function Gen2!` nos logs.


<img width="1311" height="472" alt="gc5" src="https://github.com/user-attachments/assets/a74e88d0-a93c-4ebc-9b5d-ca2399b5dd72" />
<img width="1613" height="641" alt="gc4" src="https://github.com/user-attachments/assets/9937c30e-8197-4e39-93f8-e16b65b1b8e1" />
