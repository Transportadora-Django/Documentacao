# 📑 Backlog do Projeto

Este documento apresenta o **backlog inicial** do sistema, organizado em histórias de usuário.  
Cada história contém critérios de aceite, prioridade e dependências.

---

## 👤 Cliente

<div class="backlog-section">
  <div class="backlog-card cliente">
    <div class="story-id">US-001</div>
    <h3>Solicitar orçamento rápido</h3>
    <div class="user-story">
      <p><strong>Como</strong> Cliente<br>
      <strong>Quero</strong> informar peso, distância e prazo máximo<br>
      <strong>Para</strong> receber um orçamento com as 3 opções (menor custo, mais rápido, melhor custo-benefício)</p>
    </div>
    
    <div class="acceptance-criteria">
      <h4>📋 Critérios de Aceite</h4>
      <ul>
        <li>Dado que o cliente acessa a página de simulação</li>
        <li>Quando informa peso, distância e prazo válidos</li>
        <li>Então o sistema deve exibir 3 recomendações viáveis (custo, tempo e valor final com margem)</li>
      </ul>
    </div>
    
    <div class="story-metadata">
      <span class="priority p1">P1</span>
      <span class="dependencies">📦 Frota cadastrada, Margem configurada, Preço de combustível definido</span>
    </div>
  </div>

  <div class="backlog-card cliente">
    <div class="story-id">US-002</div>
    <h3>Converter orçamento em pedido</h3>
    <div class="user-story">
      <p><strong>Como</strong> Cliente<br>
      <strong>Quero</strong> selecionar a opção de orçamento<br>
      <strong>Para</strong> gerar um pedido de frete e reservar o veículo escolhido</p>
    </div>
    
    <div class="acceptance-criteria">
      <h4>📋 Critérios de Aceite</h4>
      <ul>
        <li>Dado que existe um orçamento gerado</li>
        <li>Quando o cliente escolhe uma opção</li>
        <li>Então o pedido deve ser registrado e o veículo reservado (indisponível)</li>
      </ul>
    </div>
    
    <div class="story-metadata">
      <span class="priority p1">P1</span>
      <span class="dependencies">🔗 US-001</span>
    </div>
  </div>

  <div class="backlog-card cliente">
    <div class="story-id">US-003</div>
    <h3>Histórico de orçamentos/pedidos</h3>
    <div class="user-story">
      <p><strong>Como</strong> Cliente<br>
      <strong>Quero</strong> acessar um histórico de orçamentos/pedidos<br>
      <strong>Para</strong> acompanhar status e decisões do gerente/motorista</p>
    </div>
    
    <div class="acceptance-criteria">
      <h4>📋 Critérios de Aceite</h4>
      <ul>
        <li>O histórico deve listar pedidos com status atual (Em análise, Aprovado, Em transporte, Concluído, Recusado)</li>
      </ul>
    </div>
    
    <div class="story-metadata">
      <span class="priority p2">P2</span>
      <span class="dependencies">🔗 US-002</span>
    </div>
  </div>

  <div class="backlog-card cliente">
    <div class="story-id">US-004</div>
    <h3>Observações e janela de entrega</h3>
    <div class="user-story">
      <p><strong>Como</strong> Cliente<br>
      <strong>Quero</strong> informar observações e uma janela de entrega<br>
      <strong>Para</strong> que a viabilidade considere restrições adicionais</p>
    </div>
    
    <div class="acceptance-criteria">
      <h4>📋 Critérios de Aceite</h4>
      <ul>
        <li>O formulário de orçamento deve permitir campo de observações</li>
        <li>Se a janela de entrega for menor que o tempo estimado, o sistema deve indicar inviabilidade</li>
      </ul>
    </div>
    
    <div class="story-metadata">
      <span class="priority p3">P3</span>
      <span class="dependencies">🔗 US-001</span>
    </div>
  </div>
</div>

---

## 👤 Gerente

<div class="backlog-section">
  <div class="backlog-card gerente">
    <div class="story-id">US-005</div>
    <h3>Gerenciar frota</h3>
    <div class="user-story">
      <p><strong>Como</strong> Gerente<br>
      <strong>Quero</strong> cadastrar/editar/remover veículos<br>
      <strong>Para</strong> manter a frota atualizada</p>
    </div>
    
    <div class="acceptance-criteria">
      <h4>📋 Critérios de Aceite</h4>
      <ul>
        <li>Deve ser possível incluir veículos com tipo, capacidade, velocidade, rendimento e combustível</li>
        <li>Deve ser possível editar e remover registros</li>
      </ul>
    </div>
    
    <div class="story-metadata">
      <span class="priority p1">P1</span>
      <span class="dependencies">✅ Nenhuma</span>
    </div>
  </div>

  <div class="backlog-card gerente">
    <div class="story-id">US-006</div>
    <h3>Configurar margem de lucro</h3>
    <div class="user-story">
      <p><strong>Como</strong> Gerente<br>
      <strong>Quero</strong> definir e persistir margem de lucro<br>
      <strong>Para</strong> que os cálculos considerem automaticamente este valor</p>
    </div>
    
    <div class="acceptance-criteria">
      <h4>📋 Critérios de Aceite</h4>
      <ul>
        <li>A margem deve ser armazenada no banco de dados</li>
        <li>Todos os orçamentos devem considerar essa margem</li>
      </ul>
    </div>
    
    <div class="story-metadata">
      <span class="priority p1">P1</span>
      <span class="dependencies">✅ Nenhuma</span>
    </div>
  </div>

  <div class="backlog-card gerente">
    <div class="story-id">US-007</div>
    <h3>Manter preços de combustível</h3>
    <div class="user-story">
      <p><strong>Como</strong> Gerente<br>
      <strong>Quero</strong> atualizar preços de álcool, gasolina e diesel<br>
      <strong>Para</strong> refletir custos reais no cálculo</p>
    </div>
    
    <div class="acceptance-criteria">
      <h4>📋 Critérios de Aceite</h4>
      <ul>
        <li>Interface deve permitir edição de preços por combustível</li>
        <li>Alterações devem impactar orçamentos futuros</li>
      </ul>
    </div>
    
    <div class="story-metadata">
      <span class="priority p2">P2</span>
      <span class="dependencies">✅ Nenhuma</span>
    </div>
  </div>

  <div class="backlog-card gerente">
    <div class="story-id">US-008</div>
    <h3>Aprovar/recusar pedidos</h3>
    <div class="user-story">
      <p><strong>Como</strong> Gerente<br>
      <strong>Quero</strong> aprovar ou recusar pedidos<br>
      <strong>Para</strong> validar viabilidade e liberar execução</p>
    </div>
    
    <div class="acceptance-criteria">
      <h4>📋 Critérios de Aceite</h4>
      <ul>
        <li>Deve existir tela para aprovar ou recusar pedidos</li>
        <li>Quando recusado, pedido deve registrar justificativa</li>
        <li>Quando aprovado, veículo fica indisponível</li>
      </ul>
    </div>
    
    <div class="story-metadata">
      <span class="priority p1">P1</span>
      <span class="dependencies">🔗 US-002</span>
    </div>
  </div>

  <div class="backlog-card gerente">
    <div class="story-id">US-009</div>
    <h3>Liberar/indisponibilizar veículos</h3>
    <div class="user-story">
      <p><strong>Como</strong> Gerente<br>
      <strong>Quero</strong> liberar veículos concluídos e indisponibilizar para manutenção<br>
      <strong>Para</strong> manter disponibilidade correta da frota</p>
    </div>
    
    <div class="acceptance-criteria">
      <h4>📋 Critérios de Aceite</h4>
      <ul>
        <li>Veículo deve ser marcado como disponível após conclusão de pedido</li>
        <li>Gerente pode marcar manualmente como indisponível</li>
      </ul>
    </div>
    
    <div class="story-metadata">
      <span class="priority p2">P2</span>
      <span class="dependencies">🔗 US-005</span>
    </div>
  </div>

  <div class="backlog-card gerente">
    <div class="story-id">US-010</div>
    <h3>Relatório de lucro por período</h3>
    <div class="user-story">
      <p><strong>Como</strong> Gerente<br>
      <strong>Quero</strong> ver relatórios de lucro por período<br>
      <strong>Para</strong> avaliar desempenho operacional</p>
    </div>
    
    <div class="acceptance-criteria">
      <h4>📋 Critérios de Aceite</h4>
      <ul>
        <li>Relatório deve mostrar quantidade de pedidos, custo, receita e lucro</li>
        <li>Filtro por intervalo de datas</li>
      </ul>
    </div>
    
    <div class="story-metadata">
      <span class="priority p3">P3</span>
      <span class="dependencies">🔗 US-002, US-006, US-007</span>
    </div>
  </div>
</div>

---

## 👤 Motorista

<div class="backlog-section">
  <div class="backlog-card motorista">
    <div class="story-id">US-011</div>
    <h3>Aceitar/recusar designação</h3>
    <div class="user-story">
      <p><strong>Como</strong> Motorista<br>
      <strong>Quero</strong> visualizar e aceitar/recusar designações<br>
      <strong>Para</strong> confirmar disponibilidade para um frete</p>
    </div>
    
    <div class="acceptance-criteria">
      <h4>📋 Critérios de Aceite</h4>
      <ul>
        <li>Motorista deve ver lista de designações pendentes</li>
        <li>Deve ser possível aceitar ou recusar</li>
      </ul>
    </div>
    
    <div class="story-metadata">
      <span class="priority p2">P2</span>
      <span class="dependencies">🔗 US-008</span>
    </div>
  </div>

  <div class="backlog-card motorista">
    <div class="story-id">US-012</div>
    <h3>Atualizar status operacional</h3>
    <div class="user-story">
      <p><strong>Como</strong> Motorista<br>
      <strong>Quero</strong> atualizar status do frete (Em coleta, Em trânsito, Concluído)<br>
      <strong>Para</strong> que o sistema atualize pedido e libere veículo</p>
    </div>
    
    <div class="acceptance-criteria">
      <h4>📋 Critérios de Aceite</h4>
      <ul>
        <li>Motorista deve poder atualizar status em tempo real</li>
        <li>Pedido e veículo devem refletir o status atualizado</li>
      </ul>
    </div>
    
    <div class="story-metadata">
      <span class="priority p2">P2</span>
      <span class="dependencies">🔗 US-011</span>
    </div>
  </div>
</div>

---

## ⚙️ Sistema (transversais)

<div class="backlog-section">
  <div class="backlog-card sistema">
    <div class="story-id">US-013</div>
    <h3>Calcular e exibir recomendações</h3>
    <div class="user-story">
      <p><strong>Como</strong> Sistema<br>
      <strong>Quero</strong> calcular custo/tempo e exibir recomendações<br>
      <strong>Para</strong> apoiar decisão do cliente</p>
    </div>
    
    <div class="acceptance-criteria">
      <h4>📋 Critérios de Aceite</h4>
      <ul>
        <li>Sempre exibir 3 recomendações quando houver veículos viáveis</li>
      </ul>
    </div>
    
    <div class="story-metadata">
      <span class="priority p1">P1</span>
      <span class="dependencies">🔗 US-005, US-006, US-007</span>
    </div>
  </div>

  <div class="backlog-card sistema">
    <div class="story-id">US-014</div>
    <h3>Bloquear seleção quando inviável</h3>
    <div class="user-story">
      <p><strong>Como</strong> Sistema<br>
      <strong>Quero</strong> impedir seleção quando nenhum veículo atende capacidade/prazo<br>
      <strong>Para</strong> evitar geração de pedidos impossíveis</p>
    </div>
    
    <div class="acceptance-criteria">
      <h4>📋 Critérios de Aceite</h4>
      <ul>
        <li>Mensagem clara deve ser exibida quando não há veículos viáveis</li>
        <li>Nenhum pedido deve ser gerado nesse caso</li>
      </ul>
    </div>
    
    <div class="story-metadata">
      <span class="priority p1">P1</span>
      <span class="dependencies">🔗 US-001</span>
    </div>
  </div>

  <div class="backlog-card sistema">
    <div class="story-id">US-015</div>
    <h3>Aplicar parâmetros por tipo/combustível</h3>
    <div class="user-story">
      <p><strong>Como</strong> Sistema<br>
      <strong>Quero</strong> aplicar capacidade, velocidade, rendimento e degradação por kg de cada tipo de veículo<br>
      <strong>Para</strong> calcular corretamente custos e prazos</p>
    </div>
    
    <div class="acceptance-criteria">
      <h4>📋 Critérios de Aceite</h4>
      <ul>
        <li>Cada tipo de veículo deve considerar seus parâmetros específicos</li>
      </ul>
    </div>
    
    <div class="story-metadata">
      <span class="priority p1">P1</span>
      <span class="dependencies">🔗 US-005, US-007</span>
    </div>
  </div>

  <div class="backlog-card sistema">
    <div class="story-id">US-016</div>
    <h3>Janela de indisponibilidade</h3>
    <div class="user-story">
      <p><strong>Como</strong> Sistema<br>
      <strong>Quero</strong> bloquear veículos aprovados até conclusão/liberação<br>
      <strong>Para</strong> impedir dupla alocação</p>
    </div>
    
    <div class="acceptance-criteria">
      <h4>📋 Critérios de Aceite</h4>
      <ul>
        <li>Ao aprovar pedido, veículo deve ser marcado como indisponível</li>
        <li>Só pode ser liberado manualmente (US-009) ou pelo motorista (US-012)</li>
      </ul>
    </div>
    
    <div class="story-metadata">
      <span class="priority p1">P1</span>
      <span class="dependencies">🔗 US-008</span>
    </div>
  </div>
</div>

---

## 📊 Resumo do Backlog

| Prioridade | Cliente | Gerente | Motorista | Sistema | Total |
|------------|---------|---------|-----------|---------|-------|
| **P1** | 2 | 3 | 0 | 4 | **9** |
| **P2** | 1 | 2 | 2 | 0 | **5** |
| **P3** | 1 | 1 | 0 | 0 | **2** |
| **Total** | **4** | **6** | **2** | **4** | **16** |

---

!!! success "Sprint Planning"
    **Sugestão de Sprint 1:** Implementar todas as histórias P1 (9 histórias) para estabelecer o MVP funcional do sistema.