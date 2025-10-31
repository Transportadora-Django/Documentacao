# Protótipos de Interface - NeoCargo

Este documento apresenta os **protótipos de interface** do sistema NeoCargo, desenvolvidos no Figma para guiar o desenvolvimento do frontend.

---

## Sobre os Protótipos

Os protótipos foram criados utilizando **Figma**, uma ferramenta de design colaborativo, e representam a visão completa da interface do usuário do sistema NeoCargo.

### Características dos Protótipos

- **Ferramenta**: Figma (Design e Prototipagem)
- **Fidelidade**: Alta fidelidade com componentes interativos
- **Responsividade**: Layouts adaptados para desktop e mobile
- **Fluxos**: Navegação completa entre telas
- **Componentes**: Sistema de design consistente

### Objetivos

1. **Validação de UX**: Testar fluxos de usuário antes da implementação
2. **Guia de Desenvolvimento**: Referência visual para o frontend
3. **Comunicação**: Alinhar expectativas entre equipe e stakeholders
4. **Documentação**: Registrar decisões de design

---

## Protótipo Interativo

!!! tip "Navegação no Protótipo"
    - Use o **modo de apresentação** (ícone de play) para interagir com o protótipo
    - Clique nos elementos interativos para navegar entre telas
    - Use **Ctrl + Scroll** (ou **Cmd + Scroll** no Mac) para dar zoom
    - Para melhor experiência, abra em **tela cheia**

<iframe style="border: 1px solid rgba(0, 0, 0, 0.1);" width="100%" height="800" src="https://www.figma.com/embed?embed_host=share&url=https%3A%2F%2Fwww.figma.com%2Fdesign%2FwJgPwMoA0nEbgYlud3Qrpg%2FNeoCargo%3Fnode-id%3D0-1%26t%3DY0KFUWfXe2Yb5AFg-1" allowfullscreen></iframe>

---

## Acesso Direto ao Figma

Para visualizar e comentar diretamente no Figma, acesse:

🔗 **[Abrir Protótipo no Figma](https://www.figma.com/design/wJgPwMoA0nEbgYlud3Qrpg/NeoCargo?node-id=0-1&t=Y0KFUWfXe2Yb5AFg-1)**

---

## Principais Telas Prototipadas

### 🏠 Telas Públicas

#### Landing Page
- Apresentação do serviço
- Call-to-action para cadastro
- Destaques de funcionalidades

#### Login e Cadastro
- Formulário de autenticação
- Registro de novos usuários
- Recuperação de senha

---

### 👤 Área do Cliente

#### Dashboard
- Visão geral dos pedidos
- Estatísticas de entregas
- Atalhos rápidos

#### Novo Pedido
- Formulário de solicitação de frete
- Seleção de origem e destino
- Informações da carga

#### Cotações
- Visualização das 3 opções (econômico, rápido, custo-benefício)
- Comparação de preços e prazos
- Seleção da melhor opção

#### Meus Pedidos
- Lista de pedidos com filtros
- Status em tempo real
- Histórico completo

---

### 🚚 Área do Motorista

#### Dashboard do Motorista
- Entregas atribuídas
- Status de disponibilidade
- Estatísticas pessoais

#### Detalhes da Entrega
- Informações completas do pedido
- Rota e destino
- Contato do cliente

#### Atualização de Status
- Marcar início da entrega
- Reportar problemas
- Confirmar conclusão

---

### 👔 Área do Gerente

#### Dashboard Gerencial
- Visão geral da operação
- Pedidos pendentes de aprovação
- Métricas e KPIs

#### Gestão de Pedidos
- Aprovar/rejeitar pedidos
- Atribuir motoristas e veículos
- Acompanhamento em tempo real

#### Gestão de Frota
- Lista de veículos
- Disponibilidade
- Manutenções

#### Gestão de Motoristas
- Lista de motoristas
- Solicitações de perfil
- Histórico de entregas

---

### 👑 Área do Owner

#### Configurações do Sistema
- Ativar/desativar solicitações
- Configurar preços de combustível
- Margem de lucro

#### Gestão de Usuários
- Aprovar mudanças de perfil
- Gerenciar permissões
- Auditoria de ações

---

## Sistema de Design

### Paleta de Cores

| Cor | Hex | Uso |
|-----|-----|-----|
| **Primary** | `#2563EB` | Botões principais, links |
| **Secondary** | `#10B981` | Status positivo, sucesso |
| **Warning** | `#F59E0B` | Alertas, pendências |
| **Danger** | `#EF4444` | Erros, ações destrutivas |
| **Dark** | `#1F2937` | Textos principais |
| **Light** | `#F9FAFB` | Backgrounds |

### Tipografia

- **Fonte Principal**: Inter
- **Títulos**: 24px - 32px (Bold)
- **Subtítulos**: 18px - 20px (Semibold)
- **Corpo**: 14px - 16px (Regular)
- **Pequeno**: 12px - 13px (Regular)

### Componentes

#### Botões
- **Primary**: Ações principais (salvar, confirmar)
- **Secondary**: Ações secundárias (cancelar, voltar)
- **Outline**: Ações alternativas

#### Cards
- Sombra suave
- Bordas arredondadas (8px)
- Padding consistente

#### Formulários
- Labels claros
- Validação inline
- Mensagens de erro contextuais

---

## Fluxos de Usuário

### Fluxo: Cliente Solicita Frete

1. **Login** → Dashboard do Cliente
2. **Novo Pedido** → Preenche formulário
3. **Cotações** → Visualiza 3 opções
4. **Seleção** → Escolhe melhor opção
5. **Confirmação** → Pedido criado
6. **Acompanhamento** → Status em tempo real

### Fluxo: Gerente Aprova Pedido

1. **Login** → Dashboard Gerencial
2. **Pedidos Pendentes** → Lista de solicitações
3. **Análise** → Detalhes do pedido
4. **Atribuição** → Seleciona motorista e veículo
5. **Aprovação** → Confirma atribuição
6. **Notificação** → Motorista recebe alerta

### Fluxo: Motorista Realiza Entrega

1. **Login** → Dashboard do Motorista
2. **Entregas** → Visualiza atribuições
3. **Aceitar** → Confirma disponibilidade
4. **Iniciar** → Marca início da rota
5. **Atualizar** → Reporta progresso
6. **Concluir** → Finaliza entrega

---

## Responsividade

Os protótipos incluem versões adaptadas para diferentes tamanhos de tela:

### 🖥️ Desktop (1920x1080)
- Layout completo com sidebar
- Tabelas expandidas
- Gráficos detalhados

### 💻 Tablet (768x1024)
- Sidebar colapsável
- Tabelas responsivas
- Navegação adaptada

### 📱 Mobile (375x812)
- Menu hambúrguer
- Cards empilhados
- Navegação bottom bar

---

## Feedback e Iterações

### Como Contribuir

1. **Acesse o Figma** usando o link acima
2. **Deixe comentários** diretamente nas telas
3. **Sugira melhorias** de UX/UI
4. **Reporte inconsistências** de design

### Histórico de Versões

| Versão | Data | Mudanças |
|--------|------|----------|
| **v1.0** | Out/2025 | Versão inicial completa |
| **v1.1** | - | Ajustes de feedback (planejado) |

---

## Próximos Passos

### Em Desenvolvimento

- [ ] Implementação do frontend baseado nos protótipos
- [ ] Testes de usabilidade com usuários reais
- [ ] Ajustes de acessibilidade (WCAG 2.1)
- [ ] Animações e micro-interações

### Futuras Melhorias

- [ ] Dark mode
- [ ] Personalização de tema
- [ ] Modo offline
- [ ] PWA (Progressive Web App)

---

## Referências

- **Figma**: [Design System](https://www.figma.com/design/wJgPwMoA0nEbgYlud3Qrpg/NeoCargo)
- **Material Design**: [Guidelines](https://material.io/design)
- **Tailwind CSS**: [Documentation](https://tailwindcss.com/docs)
- **Accessibility**: [WCAG 2.1](https://www.w3.org/WAI/WCAG21/quickref/)
