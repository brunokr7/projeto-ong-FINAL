# Modelo de Site Institucional para ONG (Entrega Final)

> **Atenção:** Este repositório é um *modelo* — o nome da ONG e conteúdos estão deixados como campos/comments para você preencher.

---

## Resumo do projeto
Site institucional estático (HTML/CSS/JavaScript puro) com foco em:
- Controle de versão profissional (Git + GitFlow, commits semânticos, releases);
- Conformidade com **WCAG 2.1 Nível AA** (itens obrigatórios implementados);
- Otimização para produção (minificação de CSS/JS, imagens otimizadas);
- Deploy em **GitHub Pages**.

---

## Estrutura do repositório
```
/ (raiz)
├─ index.html
├─ about.html
├─ projetos.html
├─ contato.html
├─ css/
│  └─ styles.css
├─ js/
│  └─ main.min.js
├─ assets/
│  └─ img/
│     └─ project-sample.jpg
└─ README.md
```

---

## Como este projeto atende as **Especificações Técnicas Obrigatórias**

### 1) Controle de Versão com Git/GitHub
- **Estratégia de branching:** recomendado usar *GitFlow*:
  - `main` — branch de produção (deploy via GitHub Pages).
  - `develop` — branch de integração.
  - `feature/*` — novas funcionalidades.
  - `release/*` — preparação de release.
  - `hotfix/*` — correções emergenciais.
- **Commits semânticos:** siga o padrão [Conventional Commits]. Exemplo:
  - `feat: adicionar toggle de contraste`
  - `fix(contact): validação do formulário`
  - `chore(release): 1.0.0`
- **Releases:** use versionamento semântico `MAJOR.MINOR.PATCH`. Exemplo: `v1.0.0`.

**Sugestão de fluxo de trabalho (comandos):**
```bash
# partir do develop
git checkout -b feature/header-accessibility develop
# commits pequenos e semânticos
git add .
git commit -m "feat(header): adicionar skip-link e aria-labels"
# push e abrir PR para develop
git push -u origin feature/header-accessibility
```

### 2) Acessibilidade (WCAG 2.1 AA)
Implementações e onde estão:
- **Navegação por teclado:** `skip link` (todas as páginas), foco visível aprimorado, shortcuts simples (tecla `0` foca skip link).
- **Estrutura semântica:** uso de `<header>`, `<main>`, `<nav>`, `<footer>`, `<section>`, `<article>`, headings ordenados.
- **Contraste:** cores no tema padrão usam texto escuro sobre fundo claro; mantenha contraste mínimo 4.5:1. Há suporte a *high-contrast* (`.high-contrast`) que fornece contraste forte.
- **Leitores de tela:** atributos `aria-label`, `aria-labelledby`, `role` em landmarks e formulários com `aria-required` e `aria-describedby`.
- **Modo escuro e alto contraste acessíveis:** botões `Alto contraste` e `Modo escuro` no canto inferior que alternam classes; também respeita `prefers-color-scheme`.

> **Checklist sugerida para validação:** Lighthouse (Acessibilidade), WAVE, AXE-core (extensions).

### 3) Otimização para Produção
- **Minificação:** `css/styles.css` está em versão de desenvolvimento; `js/main.min.js` é a versão minificada pronta para produção. Para minificar o CSS você pode usar ferramentas como `csso`, `clean-css` ou serviços online antes do commit final.
- **Imagens:** `assets/img/project-sample.jpg` já está otimizada (pequeno). Para mais imagens use `imagemin`, `squoosh` ou `mozjpeg` para compressão.

---

## Documentação Técnica (README) — Instruções rápidas

### Rodando localmente
Basta abrir `index.html` no navegador (é um site estático). Para testar via servidor local (recomendado):
```bash
# Servidor simples com Python 3
python -m http.server 8000
# então abra http://localhost:8000
```

### Deploy no GitHub Pages
1. Crie um repositório público no GitHub.
2. Configure `main` como branch de publicação (ou `gh-pages` se preferir).
3. Faça push das branches:
```bash
git checkout main
git push origin main
```
4. No GitHub: Settings → Pages → Source: `main` branch → / (root).

### Pull Requests, Issues e Milestones
- Abra PRs com descrição clara, checklist de acessibilidade e instruções de teste.
- Use Issues para backlog e Milestones para versões/release planning.

---

## Checklist de entrega (marcar antes de enviar)
- [ ] Repositório **público** no GitHub.
- [ ] Histórico de commits semântico e organizado.
- [ ] Branches: `main`, `develop`, uso de `feature/*`, `release/*`.
- [ ] Releases criadas com tags semânticas (ex: `v1.0.0`).
- [ ] Todas as páginas passam em checagem básica de acessibilidade (axe/lighthouse).
- [ ] Minificação de assets incluída (`js/main.min.js` presente).
- [ ] README completo na raiz contendo instruções de deploy e justificativas.

---

## Observações finais
- Os textos principais foram deixados como comentários/espacos para preenchimento.
- Se quiser, eu posso também:
  - Gerar um exemplo de histórico de commits (um `git log --oneline`) fictício;
  - Criar um template de Pull Request e template de Issue;
  - Incluir um arquivo `release-notes.md` com modelo.

Boa sorte!