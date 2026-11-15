# Fork da Forja — `forja`

Este é um fork de `michaelladouceur1/open-pdm` mantido pela plataforma **Forja**
(`dionarley/forja`). A branch `forja` é a que o serviço usa como
dependência (path dependency); mudanças entram aqui, sem abrir PR na origem.

## O que muda nesta branch

- `HandlerRegistry::with_first(handler)` em `crates/core/src/handlers/mod.rs`:
  registra um handler antes dos embutidos, para o serviço substituir o handler
  de STEP (somente metadados) por um que tessela com o `solidcore`.

## Atualizar a partir da origem

```sh
git remote add upstream https://github.com/michaelladouceur1/open-pdm.git   # uma vez
git fetch upstream
git checkout forja
git rebase upstream/main
git push --force-with-lease origin forja
```

Se o rebase conflitar no arquivo acima, mantenha o `with_first` e resolva o
resto como vier da origem.
