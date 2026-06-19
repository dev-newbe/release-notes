# Padrão de Release Notes — Newbe

## 📋 Estrutura de Pastas

```
release-notes/
├── index.html                          # Página principal (sumário executivo)
├── notes/
│   ├── 20260612-release-notes.html    # Release de Junho 2026 (exemplo)
│   ├── 20260719-release-notes.html    # Próximo release (julho)
│   └── [YYYYMMDD-release-notes.html]  # Novo release
├── ds/
│   └── final.html                     # Design System v5.0 (referência)
├── TEMPLATE-RELEASE-NOTES.html        # Template para novos releases
└── PADRÃO-RELEASE-NOTES.md           # Este arquivo
```

## 🎨 Padrão Visual

Todos os arquivos de Release Notes **herdam os Design Tokens do DS/final.html**:
- **Cores**: Paleta completa de cores (primary, secondary, success, warning, error, info, alt)
- **Tipografia**: Quicksand (títulos) + Montserrat (interface)
- **Espaçamento**: Sistema 4pt grid
- **Componentes**: Sidebar, Topbar sticky, cards, badges, tags

## 🏗️ Estrutura HTML Padrão

### 1. **Topbar**
```html
<header class="topbar">
  <div class="brand"><div class="brand-dot"></div>newbe</div>
  <span class="version-pill">[MÊS/ANO]</span>
  <span class="topbar-desc">Release Notes — Portal RH & Plataforma</span>
  <div class="topbar-tags">
    <span class="topbar-tag pink"><i class="fa-solid fa-star"></i>[X] Novidades</span>
    <span class="topbar-tag green"><i class="fa-solid fa-arrow-up"></i>[X] Melhorias</span>
    <span class="topbar-tag"><i class="fa-solid fa-wrench"></i>[X] Correções</span>
    <a href="../index.html" class="topbar-back"><i class="fa-solid fa-arrow-left"></i>Release Notes</a>
  </div>
</header>
```

- **Brand**: Logo + dot animado + "newbe"
- **Version Pill**: Período do release (ex: "Junho 2026")
- **Topbar Tags**: Contagem visual de itens
- **Botão Voltar**: Retorna à página principal

### 2. **Sidebar**
```html
<nav class="sidebar">
  <div class="sidebar-group">Nesta Versão</div>
  <a href="#novidades"><i class="fa-solid fa-star"></i>Novidades<span class="sidebar-count pink">5</span></a>
  <a href="#melhorias"><i class="fa-solid fa-arrow-trend-up"></i>Melhorias<span class="sidebar-count green">3</span></a>
  <a href="#correcoes"><i class="fa-solid fa-wrench"></i>Correções<span class="sidebar-count amber">6</span></a>
  <div class="sidebar-group">Apresentações</div>
  <a href="#area1"><i class="fa-solid fa-briefcase"></i>Área 1</a>
</nav>
```

- **Sticky**: Fica fixa no lado esquerdo
- **Grupo de Seções**: Organizado por categoria (Nesta Versão, Apresentações)
- **Links com ícones**: Navegação rápida com contador

### 3. **Welcome Card**
```html
<div class="welcome-card">
  <div class="welcome-meta">
    <span class="tag tag-new"><i class="fa-solid fa-rocket"></i>Novo Release</span>
    <span style="font-size:11px;color:var(--color-text-muted);">Junho de 2026</span>
  </div>
  <h1 class="welcome-title">Bem-vindo ao Release de Junho 2026</h1>
  <p class="welcome-desc">Descrição executiva com impacto de negócio...</p>
</div>
```

- Abertura da página com contexto executivo
- Tom profissional e direto
- Destaca datas e destaques principais

### 4. **Summary Bar**
```html
<div class="summary-bar">
  <div class="sum-item">
    <div class="sum-icon total"><i class="fa-solid fa-list-check"></i></div>
    <div><div class="sum-value">14</div><div class="sum-label">Total de Itens</div></div>
  </div>
  <div class="sum-item">
    <div class="sum-icon pink"><i class="fa-solid fa-star"></i></div>
    <div><div class="sum-value" style="color:var(--primary-500);">5</div><div class="sum-label">Novidades</div></div>
  </div>
  <!-- Mais itens... -->
</div>
```

- KPIs visuais do release
- Ajuda colaboradores a entender o escopo rapidamente

### 5. **Seções (Novidades, Melhorias, Correções)**
```html
<section class="section" id="novidades">
  <div class="section-eyebrow">O que há de novo</div>
  <h2 class="section-title">Novidades</h2>
  <div class="section-rule"></div>

  <div class="feature-item">
    <div class="feature-header">
      <div class="feature-title">[Nome da Funcionalidade]</div>
      <div class="feature-tags">
        <span class="tag tag-new"><i class="fa-solid fa-star"></i>Novo</span>
      </div>
    </div>
    <p class="feature-desc">Descrição com impacto de negócio...</p>
    <div class="feature-audience">
      <span class="audience-label">Apresentar para</span>
      <span class="audience-pill"><i class="fa-solid fa-users"></i>Time A</span>
      <span class="audience-pill"><i class="fa-solid fa-users"></i>Time B</span>
    </div>
  </div>
</section>
```

- **Section Eyebrow**: Label pequeno identificador
- **Section Title**: Título da categoria
- **Section Rule**: Linha colorida (verde para Melhorias, âmbar para Correções)
- **Feature Items**: Cards individuais com contexto e audiência

## 📝 Guia de Preenchimento

### Informações Obrigatórias por Release

```html
<!-- No <title> -->
<title>Newbe — Release Notes · [MÊS/ANO]</title>

<!-- No version-pill -->
<span class="version-pill">[MÊS/ANO]</span>

<!-- Na topbar-tags, atualize os contadores -->
<span class="topbar-tag pink"><i class="fa-solid fa-star"></i>[X] Novidades</span>
<span class="topbar-tag green"><i class="fa-solid fa-arrow-up"></i>[X] Melhorias</span>
<span class="topbar-tag"><i class="fa-solid fa-wrench"></i>[X] Correções</span>

<!-- Na sidebar, atualize contadores -->
<span class="sidebar-count pink">[X]</span>
<span class="sidebar-count green">[X]</span>
<span class="sidebar-count amber">[X]</span>

<!-- No welcome-card -->
<h1 class="welcome-title">Bem-vindo ao Release de [MÊS/ANO]</h1>
<p class="welcome-desc">[DESCRIÇÃO EXECUTIVA]</p>

<!-- Na summary-bar -->
<div class="sum-value">[TOTAL]</div>
<div class="sum-value">[X]</div> <!-- Novidades -->
<div class="sum-value">[X]</div> <!-- Melhorias -->
<div class="sum-value">[X]</div> <!-- Correções -->

<!-- Para cada feature-item -->
<div class="feature-title">[NOME DA FUNCIONALIDADE]</div>
<p class="feature-desc">[DESCRIÇÃO COM IMPACTO]</p>
<span class="audience-pill"><i class="fa-solid fa-users"></i>[ÁREA]</span>
```

## 🔗 Convenção de Nomes

**Arquivo**: `[YYYYMMDD]-release-notes.html`
- Exemplo: `20260612-release-notes.html` (junho 12, 2026)
- Localização: `/notes/`

**URL completa**:
- `/notes/20260612-release-notes.html` (relativa do index.html)

## 🚀 Passo a Passo para Criar Novo Release

1. **Copie o TEMPLATE-RELEASE-NOTES.html** para `/notes/[YYYYMMDD]-release-notes.html`
2. **Atualize informações da topbar**: mês, ano, contadores
3. **Edite o welcome-card**: descrição executiva
4. **Preencha a summary-bar**: números totais
5. **Escreva as seções**: Novidades → Melhorias → Correções
6. **Atualize footer**: período do release
7. **Vinculhe no index.html**: adicione card no card-grid
8. **Teste os links**: topbar-back deve voltar ao index.html

## 🎯 Boas Práticas

### Textos
- ✅ **Descrições**: Diretas, focadas em impacto de negócio
- ✅ **Audiência**: Sempre especifique qual área será impactada
- ✅ **Contadores**: Mantenha sincronizados em topbar, sidebar e summary-bar

### Layout
- ✅ **Ordem**: Novidades → Melhorias → Correções
- ✅ **Hierarquia**: Welcome Card → Summary Bar → Seções detalhadas
- ✅ **Responsividade**: O layout já é responsive, não altere CSS core

### Links
- ✅ **Voltar**: Use `href="../index.html"` no topbar-back
- ✅ **Sidebar**: Use `href="#novidades"` para scroll interno
- ✅ **Index**: Use `href="notes/[YYYYMMDD]-release-notes.html"` relativo

## 📚 Referências

- **Design System**: `ds/final.html` — Todos os componentes e tokens
- **Release Atual**: `notes/20260612-release-notes.html` — Exemplo completo
- **Índice Principal**: `index.html` — Página de entrada
- **Template**: `TEMPLATE-RELEASE-NOTES.html` — Base para novos releases

---

**Última atualização**: 2026-06-19  
**Responsável**: Equipe Newbe  
**Status**: ✅ Pronto para uso em GitHub
