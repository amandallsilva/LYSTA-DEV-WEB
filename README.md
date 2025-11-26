# LYSTA - Sistema de Locação de Espaços de Eventos  
**Autores:** Amanda Silva e Francisco Martins  

---

## 🌎 Visão Geral  
A plataforma conecta **proprietários de espaços** a **clientes** que buscam locais para realizar eventos.  
Ela centraliza informações, calendário, fotos, reserva, pagamento e avaliações — tudo em um único sistema funcional e intuitivo.

---

## 🎯 Objetivo  
Desenvolver um sistema web completo para modernizar a procura e gestão de espaços para eventos, usando tecnologias diretas e acessíveis: **HTML, CSS, JavaScript, Node.js e MySQL**.

---

## 🧱 Arquitetura Base  

### **Frontend**
- **HTML5** — definição estrutural das páginas  
- **CSS3** — estilos e responsividade  
- **JavaScript (puro)** — validações e interações dinâmicas  

### **Backend**
- **Node.js + Express.js** — API web leve e simples  
- **EJS (Engine de Templates)** — páginas dinâmicas sem framework pesado  
- **Nodemailer** — envio de e-mails de confirmação e redefinição de senha  
- **bcrypt.js** — criptografia de senhas  
- **dotenv** — variáveis de ambiente  

### **Banco de Dados**
- **MySQL** — armazenamento de usuários, locais, reservas, avaliações e pagamentos  

### **Ferramentas Complementares**
- **SweetAlert2** — alertas e modais modernos  
- **Leaflet.js** — mapas simples e gratuitos  
- **Multer** — upload de fotos  
- **Axios/Fetch** — requisições assíncronas no frontend  

---

## ✨ Funcionalidades Principais  

### **Para Clientes**
- Buscar locais por data, preço, comodidades e localização  
- Visualizar disponibilidade em calendário  
- Ver detalhes completos do espaço  
- Fazer reservas e pagamentos  
- Avaliar o espaço após o evento  

### **Para Proprietários**
- Cadastrar e gerenciar seus espaços  
- Adicionar fotos, valores, taxas e regras  
- Controlar agenda via calendário  
- Acompanhar reservas (aceitar, recusar, confirmar)  
- Acompanhar avaliações recebidas  

---

## 🧭 Fluxo da Reserva  
1. Cliente seleciona datas  
2. Sistema calcula automaticamente os valores  
3. Cliente informa os dados do evento  
4. Pagamento (Pix/boleto/cartão via API)  
5. Reserva confirmada  
6. Calendário bloqueia automaticamente  
7. Após o evento → cliente avalia  

---

## 🔐 Autenticação  
- Registro de Cliente e Proprietário  
- Confirmação de e-mail  
- Login com sessão  
- Recuperação de senha  
- Segurança por **bcrypt + sessões + variáveis de ambiente**  

---

## 📡 Banco de Dados  
Modelagem baseada no diagrama de classes fornecido:

- Usuários  
- Clientes  
- Proprietários  
- Locais  
- Reservas  
- Avaliações  
- Pagamentos  

O script inicial ficará dentro de `/database/schema.sql`.

