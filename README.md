#Site Institucional para ONG (Entrega Final)



## Resumo do projeto
Site institucional estático (HTML/CSS/JavaScript puro) com foco em:
- Controle de versão profissional (Git + GitFlow, commits semânticos, releases);
- Conformidade com **WCAG 2.1 Nível AA** (itens obrigatórios implementados);
- Otimização para produção (minificação de CSS/JS, imagens otimizadas);.

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

### Controle de Versão com Git/GitHub
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

### Acessibilidade (WCAG 2.1 AA)
Implementações e onde estão:
- **Navegação por teclado:** `skip link` (todas as páginas), foco visível aprimorado, shortcuts simples (tecla `0` foca skip link).
- **Estrutura semântica:** uso de `<header>`, `<main>`, `<nav>`, `<footer>`, `<section>`, `<article>`, headings ordenados.
- **Contraste:** cores no tema padrão usam texto escuro sobre fundo claro; mantenha contraste mínimo 4.5:1. Há suporte a *high-contrast* (`.high-contrast`) que fornece contraste forte.
- **Leitores de tela:** atributos `aria-label`, `aria-labelledby`, `role` em landmarks e formulários com `aria-required` e `aria-describedby`.
- **Modo escuro e alto contraste acessíveis:** botões `Alto contraste` e `Modo escuro` no canto inferior que alternam classes; também respeita `prefers-color-scheme`.

> **Checklist sugerida para validação:** Lighthouse (Acessibilidade), WAVE, AXE-core (extensions).


---

## Documentação Técnica — Instruções rápidas

### Rodando localmente
Basta abrir `index.html` no navegador (é um site estático).


```


