# Aplicação Hello World no Google App Engine

> **O que estou fazendo:** neste exercício, uso o Cloud Shell para obter um exemplo Python, preparar o ambiente, executar uma aplicação web simples e publicá-la no Google App Engine. Os três prints registram etapas diferentes do fluxo.

## Objetivo

Entender o fluxo básico de uma aplicação Python no Google Cloud: trabalhar no Cloud Shell, preparar dependências, conferir a aplicação no navegador e realizar o deploy no App Engine.

## Print 1 — Preparação do ambiente no Cloud Shell

O primeiro print mostra o terminal do Cloud Shell, um ambiente Linux acessível pelo navegador e associado ao projeto temporário do laboratório.

1. O comando `git clone https://github.com/GoogleCloudPlatform/python-docs-samples.git` baixa para o ambiente uma cópia do repositório de exemplos Python do Google Cloud.
2. O comando `cd python-docs-samples/appengine/standard_python3/hello_world` entra na pasta do exemplo `hello_world` para o App Engine Standard com Python 3.
3. `sudo apt update` atualiza a lista local de pacotes disponíveis nos repositórios configurados. Isso não significa que todos os pacotes do sistema foram atualizados: o terminal informa que há 54 atualizações disponíveis.
4. `sudo apt install -y python3-venv` garante a ferramenta para criar ambientes virtuais Python. A saída indica que ela já estava na versão mais recente.
5. `python3 -m venv myenv` cria um ambiente virtual chamado `myenv`, isolando os pacotes Python deste exercício.
6. `source myenv/bin/activate` ativa o ambiente virtual na sessão atual do terminal.

**Resultado visível:** o código de exemplo está disponível e o ambiente Python isolado foi preparado. O print não mostra a instalação de dependências Python da aplicação nem a execução do servidor local.

**Observação:** o nome do projeto exibido no Cloud Shell é de um laboratório Qwiklabs e pode ser temporário. Não reutilize esse identificador como se fosse o projeto de produção.

## Print 2 — Aplicação aberta no navegador

O segundo print mostra a página da aplicação com a mensagem **“Hello World!”**. Isso confirma que uma versão da aplicação web respondeu com conteúdo HTML no navegador.

O endereço começa com `5000-cs-...`, formato típico de uma prévia de porta encaminhada pelo Cloud Shell. Portanto, essa tela é compatível com a visualização de um servidor de desenvolvimento executado no ambiente do Cloud Shell; ela, por si só, não comprova que a aplicação já foi implantada no App Engine. O print não mostra o comando que iniciou o servidor, então não é possível determinar somente pela imagem qual comando ou processo foi usado.

## Print 3 — Deploy concluído no App Engine

O terceiro print mostra a saída de uma implantação do serviço `default` no App Engine:

1. O processo informa que começou o deploy e que alguns arquivos foram ignorados. A mensagem recomenda `--verbosity=info` para obter mais detalhes sobre esses arquivos.
2. Cinco arquivos são enviados ao Google Cloud Storage como parte do processo de implantação.
3. O serviço `default` é atualizado. A CLI aguarda a operação do App Engine terminar e informa que a operação foi concluída.
4. A saída apresenta a URL do serviço implantado: `https://qwiklabs-gcp-233dca09c0ab577b.appspot.com`.
5. São mostrados comandos úteis para acompanhar os logs (`gcloud app logs tail -s default`) e abrir a aplicação (`gcloud app browse`).

**Resultado visível:** o App Engine aceitou e concluiu a atualização do serviço. Para confirmar o conteúdo publicado, abra a URL indicada ou execute `gcloud app browse` no ambiente correto.

**Importante:** o ID do projeto exibido neste print é diferente do ID visível no primeiro print. Isso sugere projetos ou sessões de laboratório distintos. Não se deve concluir que o navegador do print 2 está necessariamente mostrando exatamente o mesmo deploy do print 3.

## Fluxo resumido

```text
Cloud Shell
  → clonar o exemplo e entrar na pasta
  → preparar o ambiente Python
  → executar/visualizar a aplicação durante o desenvolvimento
  → implantar o serviço no App Engine
  → conferir a URL e os logs
```

## Cuidados e limpeza

- Os prints mostram identificadores de projetos de laboratório; eles podem expirar e não devem ser tratados como recursos permanentes.
- O App Engine pode gerar custos conforme o uso e a configuração da conta. Consulte o painel de faturamento e as condições do laboratório.
- Ao terminar, siga as instruções do laboratório para limpar ou encerrar recursos. Não exclua serviços ou projetos sem confirmar que são descartáveis e que você tem autorização.
- Nunca inclua neste repositório credenciais, tokens ou chaves de serviço.

## Referências


<img width="1060" height="501" alt="gc3" src="https://github.com/user-attachments/assets/b572f6d4-87b1-4c6d-95b7-edaf692114de" />
<img width="480" height="134" alt="gc2" src="https://github.com/user-attachments/assets/008c4ef1-cb07-4b1a-a05e-d67f96cb52c5" />
<img width="1610" height="811" alt="gc1" src="https://github.com/user-attachments/assets/c278ea0c-2de8-4556-ab06-badcc6ecc1d6" />

