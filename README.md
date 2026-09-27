# gestao.one — Guia de uso

Guias de **uso** do gestao.one (dono de corretora, gerente, financeiro,
vendedor). Publicado com [MkDocs Material] e servido por GitHub Pages.

🌐 **Site:** <https://renatofagalde.github.io/wiki-gestao-one/>

> A documentação **técnica** (logs, SQL, contratos por módulo, AWS) fica em outro
> repositório, **privado**: `wiki-gestao-one-tecnica`.

## Rodar localmente

```bash
python -m venv .venv && source .venv/bin/activate
pip install -r requirements.txt
mkdocs serve            # http://127.0.0.1:8000
```

## Publicar

O push na `main` dispara o workflow (`.github/workflows/deploy.yml`), que roda
`mkdocs gh-deploy` e publica na branch `gh-pages`.

## Estrutura

```
docs/
  index.md                 # porta de entrada
  uso-do-sistema/
    index.md
    cookbook.md            # do zero à comissão paga
```

[MkDocs Material]: https://squidfunk.github.io/mkdocs-material/
