# Emerald Prompt Vault Infinity

Biblioteca pessoal, universal e expansível de prompts profissionais.
Arquivo único `index.html` — funciona localmente (file://) e em GitHub Pages.

## Estrutura

- `index.html` — aplicação completa (HTML + CSS + JS + seed).
- `data/schemas/prompt.schema.json` — contrato oficial dos registros.
- `data/manifest.json` — manifesto opcional.
- `README.md` — este arquivo.

## Como usar

1. Abra `index.html` no navegador.
2. Três prompts iniciais (GOLD, DIAMOND, EMERALD) já vêm carregados.
3. Use **+ Novo** para cadastrar manualmente.
4. Use **Importar** para adicionar registros JSON.
5. Use **Exportar** para gerar backups.

## Persistência

- IndexedDB (banco `emerald-vault-db`, store `prompts`).
- Tema salvo em `localStorage` (`emerald-theme`).

## Segurança

- Conteúdo dos prompts é renderizado com `textContent` (nunca `innerHTML`).
- Importação valida e normaliza cada registro.
- IDs duplicados são sinalizados antes da confirmação.

## Esquema JSON

Veja `prompt.schema.json`. Campos obrigatórios: `id`, `title`, `content`.

## Backup e migração

1. **Exportar → Biblioteca completa** gera um `.json` com todos os prompts.
2. Em outro ambiente, abra o `index.html` e use **Importar** com o arquivo.
3. Registros com IDs existentes podem ser sobrescritos — a prévia avisa.

## Personalização

- Paleta: bloco `:root` no `<style>`.
- Categorias iniciais: renderizadas dinamicamente a partir dos dados.
- Atalhos: `Ctrl/Cmd+F` busca; `N` novo prompt; `Esc` fecha modal.

## Limitações conhecidas

- A aplicação não grava automaticamente arquivos na pasta `data/` (regra dos navegadores).
- Exportação é manual (mas sempre em JSON válido e portátil).