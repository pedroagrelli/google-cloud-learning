# Função no Cloud Run pela linha de comando

> **O que rolou aqui:** neste laboratório, preparei uma função em Node.js no Cloud Shell, publiquei uma mensagem de teste no Pub/Sub e conferi nos logs que a função foi acionada. Os prints mostram o começo da configuração e a validação no final.

## A ideia do laboratório

O objetivo é ver uma função sem servidor reagindo a um evento. Neste caso, o evento vem de um tópico do Pub/Sub: publicamos uma mensagem e a função recebe esse evento e escreve o conteúdo nos logs.

## Print 1 — Preparando o projeto no Cloud Shell

No primeiro print, o Cloud Shell está aberto no projeto temporário do Qwiklabs.

- `gcloud config set run/region us-east1` define `us-east1` como região padrão para os comandos relacionados ao Cloud Run.
- `mkdir gcf_hello_world && cd $_` cria a pasta `gcf_hello_world` e entra nela. O `$_` reaproveita o último argumento do comando anterior — nesse caso, o nome da pasta.
- Em seguida, foi digitado `package.json` sozinho. O terminal respondeu `command not found`: isso aconteceu porque o shell tentou executar esse nome como se fosse um comando. Não é um erro grave; logo depois, o arquivo foi aberto corretamente com `nano package.json`.
- `npm install` instala as dependências descritas no `package.json` e cria/atualiza o arquivo de lock das dependências.

O `npm install` terminou, mas deixou alguns avisos importantes:

- O pacote `cloudevents@0.8.0` declara suporte a versões do Node entre 16 e 22, enquanto o ambiente mostra Node `v26.13.0`. É um aviso de compatibilidade: o comando concluiu, mas vale usar a versão de Node indicada pelo laboratório para evitar problemas inesperados.
- O npm também avisou sobre uma dependência antiga (`uuid@8.3.2`) e reportou três vulnerabilidades moderadas na árvore instalada. Não rode `npm audit fix --force` às cegas: isso pode introduzir atualizações incompatíveis. Em um laboratório, confira primeiro as instruções oficiais e o resultado de `npm audit`.


## Print 2 — Publicando uma mensagem e conferindo os logs

No segundo print, uma mensagem de teste é publicada no tópico Pub/Sub `cf-demo`:

```bash
gcloud pubsub topics publish cf-demo --message="Cloud Function Gen2"
```

A resposta mostra um `messageId`, indicando que o Pub/Sub aceitou a mensagem.

Depois, o comando abaixo consulta os logs da função `nodejs-pubsub-function` na região `us-east1`:

```bash
gcloud functions logs read nodejs-pubsub-function --region=us-east1
```


## Limpeza e custos

O laboratório usa um projeto Qwiklabs temporário. Ao terminar, siga as instruções do laboratório para remover os recursos de teste, incluindo a função e os recursos Pub/Sub, se aplicável. Verifique o projeto ativo antes de apagar qualquer coisa e confira o faturamento: recursos de nuvem podem gerar custos fora dos limites ou condições do laboratório.

## Referências

<img width="1311" height="472" alt="gc5" src="https://github.com/user-attachments/assets/da9a9041-9f45-4915-9a1a-8d2c8880103a" />
<img width="1613" height="641" alt="gc4" src="https://github.com/user-attachments/assets/7850807d-4e7e-4a17-be50-574f50ac759f" />
