# Deploy de uma aplicação no Google Kubernetes Engine

Neste laboratório, fiz o seguinte:

- configurei a região para `us-east4` e a zona para `us-east4-b`;
- criei o cluster `lab-cluster` com máquinas `e2-medium`;
- conectei o `kubectl` ao cluster;
- criei o deployment `hello-server` usando a imagem `gcr.io/google-samples/hello-app:1.0`;
- expus a aplicação com um serviço `LoadBalancer` na porta `8080`;
- consultei o serviço, que ainda mostrava o IP externo como `pending` naquele momento;
- apaguei o cluster `lab-cluster` ao terminar o teste.

Resultado: o cluster foi criado, o deployment e o serviço foram configurados, e depois o cluster foi removido. A captura não confirma que a aplicação chegou a ser acessada pelo IP externo.
