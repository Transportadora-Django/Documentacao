# Diagrama UML Implementado - Sistema NeoCargo

Este documento apresenta o **diagrama de classes UML real** do sistema NeoCargo, extraído diretamente do código-fonte implementado.

---

## Sobre a Implementação

O diagrama abaixo reflete a **estrutura real das classes** implementadas no sistema, baseado nos models Django do projeto. Este é o modelo **efetivamente em produção**.

### Características da Implementação

- **Framework**: Django 4.x com ORM
- **Padrão**: MVT (Model-View-Template)
- **Banco de Dados**: PostgreSQL 14+
- **Apps Django**: contas, pedidos, rotas, veiculos, motoristas, gestao
- **Autenticação**: Django Auth + Perfis customizados

---

## Diagrama de Classes Implementado

!!! tip "Dica de Visualização"
    Para melhor visualização do diagrama:
    
    - **Zoom**: Use `Ctrl + Scroll` (Windows/Linux) ou `Cmd + Scroll` (Mac)
    - **Tela Cheia**: Clique com o botão direito e selecione "Abrir imagem em nova aba"
    - **Mermaid Live**: Copie o código e cole em [Mermaid Live Editor](https://mermaid.live/) para visualização interativa

```mermaid
classDiagram
    %% ============================================
    %% APP: CONTAS (Autenticação e Perfis)
    %% ============================================
    
    class User {
        <<Django Auth>>
        +int id
        +str username
        +str email
        +str password
        +str first_name
        +str last_name
        +bool is_active
        +bool is_staff
        +bool is_superuser
        +datetime date_joined
        +datetime last_login
    }
    
    class Profile {
        +int id
        +str role
        +datetime created_at
        +datetime updated_at
        +bool is_cliente
        +bool is_motorista
        +bool is_gerente
        +bool is_owner
    }
    
    class Role {
        <<TextChoices>>
        CLIENTE
        MOTORISTA
        GERENTE
        OWNER
    }
    
    class EmailChangeRequest {
        +int id
        +str old_email
        +str new_email
        +UUID token
        +datetime created_at
        +datetime expires_at
        +bool confirmed
        +datetime confirmed_at
        +bool is_expired
        +bool is_valid
        +save()
    }
    
    %% ============================================
    %% APP: PEDIDOS
    %% ============================================
    
    class Pedido {
        +int id
        +str cidade_origem
        +str cidade_destino
        +decimal peso_carga
        +int prazo_desejado
        +text observacoes
        +str opcao
        +str status
        +int numero_pedido_cliente
        +decimal preco_final
        +str prazo_final
        +str veiculo_final
        +decimal cotacao_economico_valor
        +decimal cotacao_economico_tempo
        +str cotacao_economico_veiculo
        +decimal cotacao_rapido_valor
        +decimal cotacao_rapido_tempo
        +str cotacao_rapido_veiculo
        +decimal cotacao_custo_beneficio_valor
        +decimal cotacao_custo_beneficio_tempo
        +str cotacao_custo_beneficio_veiculo
        +datetime created_at
        +datetime updated_at
        +bool is_cotacao
        +bool is_pendente
        +bool is_cancelado
        +bool pode_ser_cancelado()
        +bool cancelar()
        +save()
    }
    
    class StatusPedido {
        <<TextChoices>>
        COTACAO
        PENDENTE
        APROVADO
        RECUSADO
        CANCELADO
        EM_TRANSPORTE
        CONCLUIDO
    }
    
    class OpcaoCotacao {
        <<TextChoices>>
        ECONOMICO
        RAPIDO
        CUSTO_BENEFICIO
    }
    
    %% ============================================
    %% APP: ROTAS
    %% ============================================
    
    class Cidade {
        +int id
        +str nome
        +str estado
        +decimal latitude
        +decimal longitude
        +bool ativa
        +datetime created_at
        +datetime updated_at
        +str nome_completo
    }
    
    class Estado {
        <<TextChoices>>
        AC, AL, AP, AM, BA, CE, DF
        ES, GO, MA, MT, MS, MG, PA
        PB, PR, PE, PI, RJ, RN, RS
        RO, RR, SC, SP, SE, TO
    }
    
    class Rota {
        +int id
        +decimal distancia_km
        +decimal tempo_estimado_horas
        +decimal pedagio_valor
        +bool ativa
        +text observacoes
        +datetime created_at
        +datetime updated_at
        +decimal custo_estimado_combustivel
        +decimal custo_total_estimado
        +clean()
        +save()
    }
    
    class ConfiguracaoPreco {
        +int id
        +decimal preco_alcool
        +decimal preco_gasolina
        +decimal preco_diesel
        +decimal margem_lucro
        +datetime created_at
        +datetime updated_at
        +get_atual()$
    }
    
    %% ============================================
    %% APP: VEICULOS
    %% ============================================
    
    class EspecificacaoVeiculo {
        +int id
        +str tipo
        +str combustivel_principal
        +str combustivel_alternativo
        +float rendimento_principal
        +float rendimento_alternativo
        +float carga_maxima
        +int velocidade_media
        +float reducao_rendimento_principal
        +float reducao_rendimento_alternativo
        +datetime created_at
        +datetime updated_at
    }
    
    class Veiculo {
        +int id
        +str marca
        +str modelo
        +str placa
        +int ano
        +str cor
        +str categoria_minima_cnh
        +bool ativo
        +datetime created_at
        +datetime updated_at
    }
    
    class TipoVeiculo {
        <<TextChoices>>
        CARRETA
        VAN
        CARRO
        MOTO
    }
    
    class TipoCombustivel {
        <<TextChoices>>
        DIESEL
        GASOLINA
        ALCOOL
    }
    
    class CategoriaCNH {
        <<TextChoices>>
        B
        C
        D
        E
    }
    
    %% ============================================
    %% APP: MOTORISTAS
    %% ============================================
    
    class Motorista {
        +int id
        +str cnh_categoria
        +bool disponivel
        +int entregas_concluidas
        +datetime created_at
        +datetime updated_at
    }
    
    class AtribuicaoPedido {
        +int id
        +str status
        +text observacoes
        +datetime created_at
        +datetime updated_at
        +bool is_pendente
        +bool is_em_andamento
        +bool is_concluido
        +bool is_cancelado
    }
    
    class StatusAtribuicao {
        <<TextChoices>>
        PENDENTE
        EM_ANDAMENTO
        CONCLUIDO
        CANCELADO
    }
    
    class ProblemaEntrega {
        +int id
        +str tipo
        +text descricao
        +str status
        +datetime criado_em
        +datetime atualizado_em
        +datetime resolvido_em
        +text resolucao
        +bool is_pendente
        +bool is_em_analise
        +bool is_resolvido
        +Motorista motorista
        +Pedido pedido
    }
    
    class TipoProblema {
        <<TextChoices>>
        VEICULO
        CARGA
        ROTA
        CLIENTE
        ACIDENTE
        OUTRO
    }
    
    class StatusProblema {
        <<TextChoices>>
        PENDENTE
        EM_ANALISE
        RESOLVIDO
    }
    
    %% ============================================
    %% APP: GESTAO
    %% ============================================
    
    class SolicitacaoMudancaPerfil {
        +int id
        +str role_atual
        +str role_solicitada
        +text justificativa
        +str telefone
        +str cpf
        +text endereco
        +date data_nascimento
        +str cnh_categoria
        +str tipo_veiculo
        +str modelo_veiculo
        +str placa_veiculo
        +int ano_veiculo
        +str cor_veiculo
        +str status
        +text observacoes_admin
        +datetime data_aprovacao
        +datetime created_at
        +datetime updated_at
        +bool is_pendente
        +bool is_aprovada
        +bool is_rejeitada
    }
    
    class StatusSolicitacao {
        <<TextChoices>>
        PENDENTE
        APROVADA
        REJEITADA
    }
    
    class ConfiguracaoSistema {
        +int id
        +bool solicitacoes_abertas
        +text mensagem_solicitacoes_fechadas
        +datetime atualizado_em
        +get_config()$
    }
    
    %% ============================================
    %% RELACIONAMENTOS
    %% ============================================
    
    %% Contas
    User "1" --o "1" Profile : possui
    Profile ..> Role : usa
    User "1" --o "*" EmailChangeRequest : solicita
    
    %% Pedidos
    User "1" --o "*" Pedido : cria (cliente)
    Pedido ..> StatusPedido : tem
    Pedido ..> OpcaoCotacao : escolhe
    
    %% Rotas
    Cidade ..> Estado : localizada em
    Rota "*" --o "1" Cidade : origem
    Rota "*" --o "1" Cidade : destino
    
    %% Veículos
    EspecificacaoVeiculo "1" --o "*" Veiculo : especifica
    EspecificacaoVeiculo ..> TipoVeiculo : tipo
    EspecificacaoVeiculo ..> TipoCombustivel : usa
    Veiculo "*" --o "0..1" Cidade : sede_atual
    Veiculo ..> CategoriaCNH : requer
    
    %% Motoristas
    Profile "1" --o "1" Motorista : estende
    Motorista "*" --o "1" Cidade : sede_atual
    Motorista ..> CategoriaCNH : possui
    AtribuicaoPedido "*" --o "1" Motorista : atribuído a
    AtribuicaoPedido "*" --o "1" Veiculo : utiliza
    AtribuicaoPedido "1" --o "1" Pedido : executa
    AtribuicaoPedido ..> StatusAtribuicao : tem
    ProblemaEntrega "*" --o "1" AtribuicaoPedido : reportado em
    ProblemaEntrega ..> TipoProblema : tipo
    ProblemaEntrega ..> StatusProblema : status
    
    %% Gestão
    SolicitacaoMudancaPerfil "*" --o "1" User : solicitante
    SolicitacaoMudancaPerfil "*" --o "0..1" User : aprovador
    SolicitacaoMudancaPerfil "*" --o "0..1" Cidade : sede_atual
    SolicitacaoMudancaPerfil ..> StatusSolicitacao : tem
    ConfiguracaoSistema "*" --o "0..1" User : atualizado_por
```

---

## Descrição dos Módulos

### 📦 App: Contas

Gerencia autenticação, perfis de usuário e mudanças de email.

**Classes Principais:**
- `User`: Modelo padrão do Django para autenticação
- `Profile`: Extensão do usuário com roles (cliente, motorista, gerente, owner)
- `EmailChangeRequest`: Solicitações de mudança de email com token de confirmação

### 📦 App: Pedidos

Gerencia todo o ciclo de vida dos pedidos de frete.

**Classes Principais:**
- `Pedido`: Pedido de frete com cotações integradas (econômico, rápido, custo-benefício)
- Suporta múltiplos status: cotação, pendente, aprovado, em transporte, concluído

### 📦 App: Rotas

Gerencia cidades, rotas e configurações de preço.

**Classes Principais:**
- `Cidade`: Cidades atendidas pela transportadora
- `Rota`: Rotas entre cidades com distância, tempo e pedágio
- `ConfiguracaoPreco`: Preços de combustível e margem de lucro

### 📦 App: Veículos

Gerencia especificações técnicas e frota de veículos.

**Classes Principais:**
- `EspecificacaoVeiculo`: Especificações técnicas por tipo (carreta, van, carro, moto)
- `Veiculo`: Instâncias reais dos veículos da frota

### 📦 App: Motoristas

Gerencia motoristas, atribuições de entregas e problemas.

**Classes Principais:**
- `Motorista`: Dados dos motoristas (CNH, disponibilidade, entregas)
- `AtribuicaoPedido`: Atribuição de pedido a motorista e veículo
- `ProblemaEntrega`: Problemas reportados durante entregas

### 📦 App: Gestão

Gerencia solicitações de mudança de perfil e configurações do sistema.

**Classes Principais:**
- `SolicitacaoMudancaPerfil`: Solicitações de mudança de role (ex: cliente → motorista)
- `ConfiguracaoSistema`: Configurações globais (singleton)

---

## Padrões de Design Utilizados

### 1. **Strategy Pattern**
- Usado nas cotações de pedidos (econômico, rápido, custo-benefício)
- Cada estratégia calcula preço e tempo de forma diferente

### 2. **State Pattern**
- Gerenciamento de status de pedidos e atribuições
- Transições de estado controladas e validadas

### 3. **Singleton Pattern**
- `ConfiguracaoSistema` e `ConfiguracaoPreco` são singletons
- Apenas uma instância ativa por vez

### 4. **Observer Pattern**
- Sistema de notificações (implícito via signals do Django)
- Mudanças de status geram notificações automáticas

### 5. **Factory Pattern**
- Criação de pedidos com cotações automáticas
- Geração de número sequencial por cliente

---

## Estatísticas do Código

| Métrica | Valor |
|---------|-------|
| **Total de Models** | 17 classes |
| **Total de Enums** | 11 enumerações |
| **Apps Django** | 6 apps |
| **Relacionamentos** | 23 foreign keys |
| **Properties** | 35+ propriedades calculadas |
| **Métodos Customizados** | 20+ métodos |

---

## Comparação: Planejado vs Implementado

| Aspecto | Planejado | Implementado |
|---------|-----------|--------------|
| **Fonte** | Backlog e requisitos | Código real (models.py) |
| **Status** | Visão futura completa | Estado atual |
| **Detalhamento** | Conceitual | Código executável |
| **Validações** | Regras de negócio | Validators do Django |
| **Relacionamentos** | Todos previstos | Apenas criados |

---

## Próximos Passos

### Funcionalidades Planejadas (Não Implementadas)

1. **Sistema de Notificações**
   - Model `Notificacao` para alertas em tempo real
   - Integração com WebSockets

2. **Histórico de Pedidos**
   - Model `PedidoHistorico` para auditoria completa
   - Rastreamento de todas as mudanças

3. **Avaliações e Feedback**
   - Model `Avaliacao` para clientes avaliarem entregas
   - Sistema de rating para motoristas

4. **Dashboard e Analytics**
   - Models para métricas e KPIs
   - Relatórios gerenciais

---

## Referências

- **Código Fonte**: `/NeoCargo/backend/apps/*/models.py`
- **Migrations**: `/NeoCargo/backend/apps/*/migrations/`
- **Testes**: `/NeoCargo/backend/apps/*/tests/test_models.py`
- **Documentação Django**: [Django Models](https://docs.djangoproject.com/en/4.2/topics/db/models/)
