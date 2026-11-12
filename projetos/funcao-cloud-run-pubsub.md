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

**Em resumo:** a pasta e as dependências foram preparadas. O print não mostra todo o código da função nem o comando de deploy, então não dá para afirmar por ele sozinho como esses passos foram feitos.

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

Entre as entradas aparece `LOG: Hello, Cloud Function Gen2!`. Esse é o resultado esperado: a função recebeu a mensagem e registrou o texto nos logs. Também aparecem registros de inicialização da instância e da verificação de saúde do contêiner (`STARTUP TCP probe`), que indicam a inicialização do serviço — não são, por si só, erros.

**Em resumo:** o print confirma o caminho do evento: publicação no Pub/Sub → execução da função → mensagem visível nos logs.

## O que aprendi

- O Cloud Shell permite criar e configurar os arquivos do exercício sem instalar ferramentas localmente.
- O Pub/Sub pode disparar uma função quando uma mensagem é publicada em um tópico.
- Os logs ajudam a confirmar se a função recebeu e processou o evento.
- Avisos de versão e vulnerabilidades merecem atenção, mesmo quando a instalação termina com sucesso.

## Observação sobre as imagens

As duas imagens aparecem nesta conversa, mas não encontrei arquivos de imagem correspondentes na árvore do repositório. Por isso, este documento explica cada print, mas ainda não consegue exibi-los aqui. Quando os arquivos forem enviados ao repositório (por exemplo, em `projetos/imagens/cloud-run-function-01.png` e `projetos/imagens/cloud-run-function-02.png`), posso inserir as imagens junto às seções correspondentes.

## Limpeza e custos

O laboratório usa um projeto Qwiklabs temporário. Ao terminar, siga as instruções do laboratório para remover os recursos de teste, incluindo a função e os recursos Pub/Sub, se aplicável. Verifique o projeto ativo antes de apagar qualquer coisa e confira o faturamento: recursos de nuvem podem gerar custos fora dos limites ou condições do laboratório.

## Referências

- [Cloud Run functions — documentação](https://cloud.google.com/run/docs/functions/overview)
- [Pub/Sub — documentação](https://cloud.google.com/pubsub/docs/overview)
- [Google Cloud CLI: publicar mensagens em tópicos](https://cloud.google.com/sdk/gcloud/reference/pubsub/topics/publish)
- [Google Cloud CLI: ler logs de funções](https://cloud.google.com/sdk/gcloud/reference/functions/logs/read)
