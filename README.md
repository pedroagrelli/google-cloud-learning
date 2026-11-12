# Google Cloud Learning

Repositório pessoal para organizar meus estudos sobre Google Cloud Platform (GCP), registrar práticas e guardar anotações úteis para consultas futuras.

> **Status:** o repositório ainda não tinha arquivos de estudo. Este README estabelece uma estrutura inicial; os tópicos abaixo são sugestões, não atividades que já foram concluídas.

## Objetivos

- Aprender os conceitos e serviços principais do Google Cloud.
- Registrar o que foi estudado, comandos usados e resultados observados.
- Documentar exercícios e projetos de forma que eu possa reproduzi-los depois.
- Manter notas claras, incluindo dúvidas, erros encontrados e links para documentação oficial.

## Organização sugerida

À medida que os estudos avançarem, posso organizar o conteúdo por tema:

```text
.
├── README.md
├── fundamentos/
│   └── README.md
├── computacao/
│   └── README.md
├── armazenamento-e-bancos-de-dados/
│   └── README.md
├── redes-e-seguranca/
│   └── README.md
├── dados-e-analytics/
│   └── README.md
└── projetos/
    └── README.md
```

Cada pasta pode começar com seu próprio `README.md`, explicando o assunto e descrevendo o propósito dos arquivos de texto daquele tema. Os diretórios são uma proposta: posso adaptá-los conforme o curso ou a trilha de estudos.

## O que documentar em cada arquivo de texto

Para que cada nota seja compreensível sem depender da memória, incluir no início do arquivo uma breve descrição do que estou fazendo e, quando fizer sentido, registrar:

1. **Objetivo:** o que quero aprender ou construir.
2. **Conceitos:** serviços e ideias estudados, com minhas próprias palavras.
3. **Passos:** o que fiz, em ordem, e os comandos relevantes.
4. **Resultado:** o que aconteceu e como confirmei que funcionou.
5. **Problemas e soluções:** erros encontrados e como foram resolvidos.
6. **Limpeza:** recursos de nuvem que precisam ser removidos para evitar custos.
7. **Referências:** links para documentação oficial e materiais consultados.

### Modelo para novas anotações

```markdown
# Título do estudo

> **O que estou fazendo:** resumo curto do exercício e do que pretendo aprender.

## Objetivo

## Conceitos estudados

## Passos realizados

## Resultado

## Problemas e soluções

## Limpeza de recursos

## Referências
```

## Cuidados com custos e segurança

- Antes de criar recursos, verificar preços, cotas e a região escolhida.
- Apagar os recursos de teste quando não forem mais necessários e confirmar que foram removidos.
- Não publicar senhas, chaves de serviço, tokens, arquivos `.env` nem dados pessoais.
- Preferir credenciais temporárias e permissões mínimas necessárias para cada exercício.
- Se algum arquivo contiver informação sensível, removê-la do histórico e rotacionar a credencial; apenas apagar o arquivo atual pode não ser suficiente.

## Como usar este repositório

1. Criar uma pasta para o tema ou serviço estudado.
2. Adicionar um arquivo Markdown (`.md`) com o objetivo e os passos do exercício.
3. Registrar o resultado, os aprendizados e as referências.
4. Revisar as instruções de limpeza e remover recursos que possam gerar cobrança.
5. Atualizar este README quando a estrutura do repositório mudar.

## Referências

- [Documentação do Google Cloud](https://cloud.google.com/docs)
- [Google Cloud Skills Boost](https://www.cloudskillsboost.google/)
- [Preços do Google Cloud](https://cloud.google.com/pricing)
