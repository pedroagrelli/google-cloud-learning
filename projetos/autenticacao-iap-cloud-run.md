# Autenticação de usuários com Identity-Aware Proxy

Neste laboratório, fiz o seguinte:

- baixei e extraí os arquivos de exemplo do laboratório no Cloud Shell;
- implantei a aplicação `HelloWorld` como serviço `user-auth-lab` no Cloud Run, na região `us-central1`;
- habilitei o Identity-Aware Proxy (IAP) e concedi à minha conta acesso ao serviço;
- atualizei a aplicação e testei o endpoint com `curl`.

Resultado: o serviço foi implantado e respondeu ao teste com a mensagem `Hello, totally fake email!`. Depois, desabilitei o IAP e habilitei acesso público para testar o serviço sem autenticação.
