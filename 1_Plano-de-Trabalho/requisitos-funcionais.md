# 2. Requisitos Funcionais

## 2.1 Autenticação e Usuários  

### RF-001 — Cadastro  
- O usuário escolhe entre: **Cliente** ou **Proprietário**.  
- Campos obrigatórios: nome, e-mail, telefone, senha e confirmação de senha.  
- Validação de formato do e-mail e senhas iguais.  
- Confirmação de e-mail obrigatória para ativar a conta.  

### RF-002 — Login  
- Acesso por e-mail e senha.  
- Opção “lembrar-me”.  
- Link “esqueci minha senha”.  

### RF-003 — Recuperação de senha  
- Usuário informa o e-mail.  
- Sistema envia link seguro para redefinir.  


---

## 2.2 Cadastro e Gestão de Locais  

### RF-004 — Cadastro Completo do Local  
Estruturado em quatro etapas:
1. **Informações básicas:** nome do local, tipo de espaço, descrição e capacidade.  
2. **Endereço:** CEP, número, complemento, bairro, cidade, UF e instruções de acesso.  
3. **Preços e taxas:** valor da diária, entrada exigida, caução, taxa de limpeza e comodidades disponíveis.  
4. **Fotos e regras:** upload de imagens e regras gerais do espaço.  

### RF-005 — Upload de Fotos  
- Mínimo de 3 e máximo de 10 fotos.  
- Formatos aceitos: JPG, PNG, WebP.  
- Primeira foto é definida como capa.  

### RF-006 — Calendário de Disponibilidade  
- Visualização mensal com até 24 meses futuros.  
- Proprietário marca indisponibilidades.  
- Ajuste de preços por dia (preço especial).  
- Bloqueio automático após confirmação da reserva.  

### RF-007 — Status do Anúncio  
- Rascunho  
- Pendente de aprovação  
- Publicado  
- Pausado  
- Arquivado  


---

## 2.3 Busca e Filtros  

### RF-008 — Busca Principal  
- Campo de busca por localização.  
- Opção “usar localização atual”.  
- Seleção de check-in e check-out.  

### RF-009 — Filtros Avançados  
- Preço  
- Tipo de espaço  
- Comodidades  
- Avaliação mínima  

### RF-010 — Lista de Resultados  
Cada card do espaço deve mostrar:  
- Foto principal  
- Disponibilidade (badge)  
- Nome do local  
- Localização (cidade e bairro)  
- Avaliação média  
- Preço da diária  

### RF-011 — Mapa Interativo  
- Pinos indicando locais.  
- Verde = disponível nas datas escolhidas  
- Vermelho = indisponível  


---

## 2.4 Página de Detalhes do Local  

### RF-012 — Elementos obrigatórios  
- Carrossel de fotos  
- Endereço e localização  
- Tipo de espaço, capacidade e comodidades  
- Mapa ilustrativo  
- Descrição completa  
- Regras e taxas adicionais  
- Mini-calendário  
- Avaliações  
- Botões móveis (reservar, favoritar, compartilhar)  


---

## 2.5 Sistema de Reservas e Pagamento  

### RF-013 — Fluxo de Reserva  
1. Seleção de datas  
2. Resumo financeiro automático  
3. Dados do evento  
4. Pagamento (Pix, cartão ou boleto)  
5. Confirmação e bloqueio da disponibilidade  

### RF-014 — Gestão de Reservas  
**Cliente:** pendentes, confirmadas, concluídas, canceladas  
**Proprietário:** solicitações, confirmadas, concluídas, canceladas  

### RF-015 — Políticas de Cancelamento  
- Flexível  
- Moderada  
- Rigorosa  
- Personalizada  


---

## 2.6 Sistema de Avaliações  

### RF-016 — Avaliação Pós-Estadia  
- Notas para limpeza, atendimento e custo-benefício  
- Comentário opcional  
- Possibilidade de enviar até 5 fotos  
- Você pode editar em até 24h  
