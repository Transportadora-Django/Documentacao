# 📘 Projeto — Técnicas de Programação para Plataformas Emergentes (FGA0242)

<div class="hero">
  <div class="hero-content">
    <h1>
      <img src="assets/Logo-NeoCargo.svg" alt="NeoCargo Logo" class="hero-logo">
    </h1>
    <p>Sistema inteligente de simulação e alocação de veículos para transporte de cargas</p>
  </div>
</div>

Este projeto integra a disciplina **Técnicas de Programação para Plataformas Emergentes (FGA0242)** e tem como objetivo demonstrar todas as etapas de um desenvolvimento de software **de ponta a ponta**: levantamento e análise, modelagem, implementação, testes e documentação.

---

## 🔎 Ponto de Partida (Reaproveitamento de Código)

O projeto **não** parte apenas do enunciado: ele utiliza e **reaproveita implementações existentes** do repositório base, reorganizando-as no padrão Django (MVT) e **ampliando a regra de negócio** (ex.: novas histórias de usuário, perfis Gerente/Motorista/Cliente).

!!! info "Repositório Base"
    👉 [https://github.com/wagnermc506/OOP_ep2_mirror/tree/master](https://github.com/wagnermc506/OOP_ep2_mirror/tree/master)

---

## 🎯 Objetivo do Sistema

<div class="system-objectives">
  <div class="system-goal">
    <h3>🎯 Meta Principal</h3>
    <p>Construir um sistema de simulação e alocação de veículos para fretes que:</p>
  </div>
</div>

<div class="features-list">
  <div class="feature-item">
    <span class="feature-check">📊</span>
    <div>
      <strong>Entrada de Dados</strong>
      <p>Receba peso, distância e prazo de entrega</p>
    </div>
  </div>

  <div class="feature-item">
    <span class="feature-check">💰</span>
    <div>
      <strong>Cálculo Inteligente</strong>
      <p>Calcule tempo e custo por tipo de veículo (com margem de lucro e preço de combustível)</p>
    </div>
  </div>

  <div class="feature-item">
    <span class="feature-check">🏆</span>
    <div>
      <strong>Três Recomendações</strong>
      <p>Exiba opções: menor custo, mais rápido e melhor custo-benefício</p>
    </div>
  </div>

  <div class="feature-item">
    <span class="feature-check">🔒</span>
    <div>
      <strong>Controle de Disponibilidade</strong>
      <p>Bloqueie o veículo selecionado até a liberação</p>
    </div>
  </div>

  <div class="feature-item">
    <span class="feature-check">💾</span>
    <div>
      <strong>Persistência de Dados</strong>
      <p>Persista frota, preços e margem de lucro</p>
    </div>
  </div>
</div>

---

## ⚙️ Tecnologias

<div class="tech-grid">
  <div class="tech-card">
    <div class="tech-icon">🐍</div>
    <h3>Backend</h3>
    <p>Django (arquitetura MVT)</p>
  </div>
  
  <div class="tech-card">
    <div class="tech-icon">🎨</div>
    <h3>Frontend</h3>
    <p>Templates do Django com HTML, CSS e JavaScript (padrão do Django)</p>
  </div>
  
  <div class="tech-card">
    <div class="tech-icon">🐳</div>
    <h3>Infra</h3>
    <p>Docker (containerização)</p>
  </div>
  
  <div class="tech-card">
    <div class="tech-icon">📖</div>
    <h3>Docs</h3>
    <p>MkDocs</p>
  </div>
</div>

---

## 📚 Navegação da Documentação

<div class="navigation-grid">
  <a href="04-brainstorm-historias/" class="nav-card-link">
    <div class="nav-card">
      <div class="nav-number">01</div>
      <h3>Brainstorm de Histórias</h3>
      <p>Ideação e desenvolvimento das funcionalidades do sistema</p>
    </div>
  </a>

  <a href="05-backlog/" class="nav-card-link">
    <div class="nav-card">
      <div class="nav-number">02</div>
      <h3>Backlog</h3>
      <p>Priorização e organização das demandas do projeto</p>
    </div>
  </a>
</div>
