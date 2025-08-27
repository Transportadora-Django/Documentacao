# 💡 Brainstorm de Histórias de Usuário

Este documento reúne o **brainstorm de histórias de usuário** para o sistema de simulação e alocação de veículos.  
O objetivo é ampliar a regra de negócio, incorporando novos perfis (Gerente, Motorista, Cliente) e funcionalidades adicionais ao projeto base.

---

## 👤 Cliente

<div class="user-stories-grid">
  <div class="story-card cliente">
    <div class="story-number">01</div>
    <h3>Solicitar orçamento rápido</h3>
    <p><em>Como Cliente, quero informar peso, distância e prazo máximo para receber um orçamento com as 3 opções (menor custo, mais rápido, melhor custo-benefício) e poder decidir.</em></p>
  </div>

  <div class="story-card cliente">
    <div class="story-number">02</div>
    <h3>Converter orçamento em pedido</h3>
    <p><em>Como Cliente, quero selecionar a opção desejada do orçamento para gerar um pedido de frete, bloqueando o veículo escolhido se viável.</em></p>
  </div>

  <div class="story-card cliente">
    <div class="story-number">03</div>
    <h3>Histórico de orçamentos/pedidos</h3>
    <p><em>Como Cliente, quero consultar meu histórico com status (Em análise, Aprovado, Em transporte, Concluído, Recusado).</em></p>
  </div>

  <div class="story-card cliente">
    <div class="story-number">04</div>
    <h3>Observações e janela de entrega</h3>
    <p><em>Como Cliente, quero informar observações (ex.: janela de coleta/entrega) para que a viabilidade considere o tempo máximo indicado.</em></p>
  </div>
</div>

---

## 👤 Gerente

<div class="user-stories-grid">
  <div class="story-card gerente">
    <div class="story-number">05</div>
    <h3>Gerenciar frota</h3>
    <p><em>Como Gerente, quero cadastrar/editar/remover veículos (tipo, capacidade, velocidade, rendimento, combustível) para manter a frota atualizada.</em></p>
  </div>

  <div class="story-card gerente">
    <div class="story-number">06</div>
    <h3>Configurar margem de lucro (persistente)</h3>
    <p><em>Como Gerente, quero definir/alterar a margem de lucro padrão e que ela fique persistida para os cálculos.</em></p>
  </div>

  <div class="story-card gerente">
    <div class="story-number">07</div>
    <h3>Manter preços de combustível</h3>
    <p><em>Como Gerente, quero atualizar os preços de álcool, gasolina e diesel usados no cálculo do custo.</em></p>
  </div>

  <div class="story-card gerente">
    <div class="story-number">08</div>
    <h3>Aprovar/recusar pedidos</h3>
    <p><em>Como Gerente, quero aprovar pedidos viáveis e recusar os inviáveis (sem veículo dentro de peso/tempo), registrando justificativa.</em></p>
  </div>

  <div class="story-card gerente">
    <div class="story-number">09</div>
    <h3>Liberar/indisponibilizar veículos</h3>
    <p><em>Como Gerente, quero liberar veículos ao concluir fretes e também indisponibilizá-los manualmente para manutenção.</em></p>
  </div>

  <div class="story-card gerente">
    <div class="story-number">10</div>
    <h3>Relatório de lucro por período</h3>
    <p><em>Como Gerente, quero ver um resumo por período (pedidos atendidos, lucro estimado vs. realizado).</em></p>
  </div>
</div>

---

## 👤 Motorista

<div class="user-stories-grid">
  <div class="story-card motorista">
    <div class="story-number">11</div>
    <h3>Aceitar/recusar designação</h3>
    <p><em>Como Motorista, quero visualizar minha designação de frete e aceitar/recusar, ajustando disponibilidade do veículo.</em></p>
  </div>

  <div class="story-card motorista">
    <div class="story-number">12</div>
    <h3>Atualizar status operacional</h3>
    <p><em>Como Motorista, quero marcar "Em coleta", "Em trânsito", "Concluído" para que o sistema libere o veículo e atualize o pedido.</em></p>
  </div>
</div>

---

## ⚙️ Regras Transversais (Sistema)

<div class="user-stories-grid">
  <div class="story-card sistema">
    <div class="story-number">13</div>
    <h3>Calcular e exibir recomendações</h3>
    <p><em>Como Sistema, devo calcular custo/tempo por veículo e exibir as 3 recomendações (menor custo, mais rápido, melhor custo-benefício) apenas para veículos viáveis.</em></p>
  </div>

  <div class="story-card sistema">
    <div class="story-number">14</div>
    <h3>Bloquear seleção quando inviável</h3>
    <p><em>Como Sistema, devo impedir a seleção quando nenhum veículo atende capacidade/prazo, exibindo explicação.</em></p>
  </div>

  <div class="story-card sistema">
    <div class="story-number">15</div>
    <h3>Aplicar parâmetros por tipo/combustível</h3>
    <p><em>Como Sistema, devo aplicar capacidade, velocidade, rendimento e degradação por kg, além do preço do combustível correspondente.</em></p>
  </div>

  <div class="story-card sistema">
    <div class="story-number">16</div>
    <h3>Janela de indisponibilidade</h3>
    <p><em>Como Sistema, ao aprovar um pedido devo bloquear o veículo no período estimado, impedindo dupla alocação até liberação.</em></p>
  </div>
</div>

---

## 📊 Resumo por Perfil

| Perfil | Quantidade de Histórias | Foco Principal |
|--------|------------------------|----------------|
| **Cliente** | 4 histórias | Solicitar orçamentos e acompanhar pedidos |
| **Gerente** | 6 histórias | Gestão operacional e controle financeiro |
| **Motorista** | 2 histórias | Execução e atualização de status |
| **Sistema** | 4 histórias | Regras de negócio e validações |
| **Total** | **16 histórias** | Cobertura completa do fluxo |

---

!!! tip "Próximos Passos"
    Este brainstorm será refinado no **[Backlog](05-backlog.md)** com critérios de aceite, priorização e estimativas de esforço.