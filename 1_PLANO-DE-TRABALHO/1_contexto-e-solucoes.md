# 📘 LYSTA - Documentação Técnica e Funcional

**Versão:** 1.0.0  
**Status:** MVP (Produto Mínimo Viável) Concluído  
**Desenvolvedor(a):** Amanda e Francisco

---

## 1. Visão Geral e Contexto

### 1.1 O Problema
Encontrar locais para eventos (casamentos, aniversários, reuniões) na região de Itacoatiara-AM é um processo manual, descentralizado e burocrático. Clientes dependem de indicações informais e proprietários têm dificuldade em gerenciar suas agendas.

### 1.2 A Solução (LYSTA)
Uma plataforma web centralizada (Marketplace) que conecta proprietários de espaços a clientes. O sistema automatiza a vitrine (fotos/preços), a verificação de disponibilidade (calendário) e o processo de reserva, garantindo segurança e agilidade para ambas as partes.

---

## 2. Arquitetura e Tecnologias

O sistema foi construído utilizando a arquitetura **MVC (Model-View-Controller)** simplificada, focada em renderização no lado do servidor (SSR).

### Stack Tecnológico:
* **Backend (Servidor):** Node.js com Express.
* **Frontend (Interface):** EJS (Embedded JavaScript Templating), HTML5, CSS3 (Design Responsivo).
* **Banco de Dados:** MySQL (Relacional).
* **Bibliotecas Principais:**
    * `mysql2`: Conexão com banco de dados.
    * `bcryptjs`: Criptografia de senhas (Segurança).
    * `express-session`: Gestão de sessões de login.
    * `multer`: Gerenciamento de upload de arquivos (fotos).
    * `flatpickr`: Calendário interativo no frontend.

---

## 3. Requisitos e Funcionalidades

### 3.1 Módulo de Autenticação
* **Cadastro Dual:** Usuário pode se cadastrar como `Cliente` (busca espaços) ou `Proprietário` (anuncia espaços).
* **Login Seguro:** Autenticação via e-mail e senha criptografada.
* **Proteção de Rotas:** Páginas administrativas (Dashboard, Edição) inacessíveis sem login.

### 3.2 Módulo de Espaços (Proprietário)
* **CRUD Completo:** Criar, Ler, Atualizar e Deletar anúncios.
* **Upload de Fotos:** Suporte para múltiplas imagens (capa + galeria) com armazenamento local na pasta `/public/uploads`.
* **Limite de Segurança:** Validação para máximo de 5 fotos por espaço.
* **Gestão de Comodidades:** Seleção de itens (Wi-Fi, Piscina, etc.) via checkbox.

### 3.3 Módulo de Busca e Reserva (Cliente)
* **Busca Inteligente:** Filtros combinados por:
    * *Localização (Bairro)*
    * *Preço Máximo*
    * *Disponibilidade de Data (SQL Query que exclui espaços já ocupados)*
* **Cálculo Automático:** Valor da diária + 10% de taxa de serviço calculado em tempo real no frontend.
* **Bloqueio de Calendário:** O sistema impede reservas duplicadas para a mesma data utilizando a biblioteca Flatpickr integrada ao backend.

### 3.4 Módulo Social e Feedback
* **Avaliações (Reviews):** Clientes podem dar nota (1-5 estrelas) e comentar.
* **Regra de Negócio:** A avaliação só é permitida após a data do evento ter passado e se a reserva estiver confirmada.

---

## 4. Fluxos de Usuário (User Flow)

### 👤 Fluxo do Cliente
1.  **Home:** Pesquisa por data, bairro e preço.
2.  **Detalhes:** Vê fotos em galeria interativa, descrição e comodidades.
3.  **Reserva:** Seleciona data livre no calendário -> Escolhe pagto (Pix/Cartão) -> Confirma.
4.  **Pós-Evento:** Acessa Dashboard -> Clica em "Avaliar" -> Envia feedback que aparece publicamente.

### 🏠 Fluxo do Proprietário
1.  **Dashboard:** Visualiza resumo de reservas recebidas e lista de imóveis cadastrados.
2.  **Anunciar:** Preenche formulário -> Sobe fotos do computador -> Publica.
3.  **Gestão:** Recebe notificação de reserva no Painel -> Entra em contato via WhatsApp (Botão integrado).
4.  **Manutenção:** Edita preços, textos, gerencia fotos (capa/exclusão) ou deleta anúncios antigos.

---

## 5. Estrutura do Banco de Dados (Schema)

O banco `lysta_db` é composto pelas seguintes tabelas relacionais:

1.  **`users`**: Armazena dados de login, tipo de conta (client/owner) e contato.
2.  **`spaces`**: Dados do imóvel (preço, endereço, fk_owner).
3.  **`space_images`**: Links para as fotos salvas fisicamente no servidor.
4.  **`bookings`**: Registra quem alugou o quê, datas, valores e status (confirmed/pending/cancelled).
5.  **`reviews`**: Comentários e notas vinculados a um espaço e usuário.
6.  **`amenities` & `space_amenities`**: Tabela pivô para relacionar características (N:N).

---

## 6. Histórico de Desenvolvimento

O projeto foi construído em ciclos incrementais:

1.  **Fase 1 - Fundação:** Configuração do Node.js, criação do Banco de Dados MySQL e conexão (`db.js`).
2.  **Fase 2 - Segurança:** Implementação do sistema de Login/Cadastro com hash de senhas e sessões.
3.  **Fase 3 - Core do Proprietário:** Criação do formulário de anúncio e salvamento no banco.
4.  **Fase 4 - Core do Cliente:** Criação da Home, Listagem e Página de Detalhes.
5.  **Fase 5 - Mídia:** Implementação do `Multer` para upload de fotos reais.
6.  **Fase 6 - Lógica de Negócio:** Sistema de Reservas, cálculo de preços e bloqueio de datas ocupadas.
7.  **Fase 7 - Dashboard & Gestão:** Painel administrativo, edição de espaços e botão de delete.
8.  **Fase 8 - Refinamento Visual (UI/UX):** Aplicação da identidade visual "Laranja/Creme", tipografia moderna e copywriting estratégico.

---

## 7. Como Rodar o Projeto

Para instalar este sistema em uma nova máquina, siga os passos abaixo:

### Pré-requisitos
* Node.js instalado.
* MySQL Workbench instalado e rodando.

### Passo a Passo

1.  **Banco de Dados:**
    Abra o MySQL Workbench e execute o script SQL de criação do banco `lysta_db` e suas tabelas.

2.  **Instalação das Dependências:**
    Abra o terminal na pasta do projeto e execute:
    ```bash
    npm install
    ```

3.  **Configuração:**
    Verifique se a senha do seu banco de dados local está correta no arquivo `db.js`.

4.  **Execução:**
    Inicie o servidor local:
    ```bash
    node app.js
    ```

5.  **Acesso:**
    Abra o navegador e acesse: `http://localhost:3000`
