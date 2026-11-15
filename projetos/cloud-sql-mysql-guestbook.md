# Banco MySQL para o Guestbook no Cloud SQL

Neste laboratório, fiz o seguinte:

- conectei à instância MySQL `myinstance` pelo Cloud SQL Proxy usando o usuário `root`;
- criei o banco de dados `guestbook`;
- criei a tabela `entries` com os campos `guestName`, `content` e `entryID`;
- inseri duas mensagens de teste na tabela;
- consultei os registros com `SELECT * FROM entries`.

Resultado: a consulta retornou as duas mensagens inseridas, com seus respectivos IDs.
