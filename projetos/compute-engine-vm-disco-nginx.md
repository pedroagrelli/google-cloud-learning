# Máquina virtual, disco e servidor web no Compute Engine

Neste laboratório, fiz o seguinte:

- criei um bucket do Cloud Storage na região `US`;
- configurei a zona `us-central1-c`;
- criei a VM `my-instance` com Debian 12 e tipo `e2-medium`;
- criei a regra de firewall `default-allow-http` para permitir tráfego HTTP na porta 80;
- criei o disco persistente `mydisk` de 200 GB e conectei à VM;
- conectei à VM por SSH e iniciei a atualização dos pacotes e a instalação do Nginx.

Resultado: a VM ficou em execução, o disco foi criado e anexado, e a regra de firewall foi configurada. As capturas não mostram a conclusão da instalação do Nginx nem a formatação e montagem do disco.
<img width="1368" height="978" alt="gc9" src="https://github.com/user-attachments/assets/c23136aa-c4ed-40de-a3ba-bf6ca89cbcf3" />
<img width="1918" height="991" alt="gc8" src="https://github.com/user-attachments/assets/81325b52-350c-49f6-b51f-87b68dded5bd" />
