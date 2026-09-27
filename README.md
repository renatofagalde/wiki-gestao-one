# gestao.one — Docs técnicas

Documentação técnica e de operação do gestao.one, **organizada por módulo**
(`app-cam`, `app-not`, `app-cms`, …). Publicada com [MkDocs Material] e servida
por GitHub Pages.

> ⚠️ **Repositório público.** Nunca inclua dado real: e-mail de pessoa, `user_id`,
> `hash` de corretora, IP, token ou credencial. Use sempre placeholders
> (`pessoa.exemplo@gmail.com`, `01a0e300-0000-…`). Comandos e queries, sim; dados
> de produção/cliente, não.

## Rodar localmente

```bash
python -m venv .venv && source .venv/bin/activate
pip install -r requirements.txt
mkdocs serve            # http://127.0.0.1:8000
```

## Publicar

O push na `main` dispara o workflow (`.github/workflows/deploy.yml`), que roda
`mkdocs gh-deploy` e publica na branch `gh-pages`. O site fica em
<https://renatofagalde.github.io/wiki/>.

## Estrutura

```
docs/
  index.md            # porta de entrada
  app-cam/            # autenticação, contas, convites, RBAC
  app-not/            # notificações / e-mail
  app-cms/            # conteúdo
```

Cada módulo segue o mesmo padrão: visão geral, logs & CloudWatch, consultas SQL,
casos resolvidos.

[MkDocs Material]: https://squidfunk.github.io/mkdocs-material/
