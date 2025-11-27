## 📌 Diagrama de Caso de Uso — Sistema de Locação LYSTA

O diagrama de caso de uso representa, de forma visual e simplificada, as principais interações que os atores têm com o sistema de locação de espaços.  
Ele descreve **o que** o sistema deve oferecer do ponto de vista funcional, sem entrar ainda em questões técnicas de interface, dados ou implementação.

No contexto do LYSTA, três atores desempenham papéis fundamentais:

- **Cliente**: busca locais, visualiza informações, realiza reservas, efetua pagamentos e avalia espaços utilizados.
- **Proprietário**: cadastra e gerencia seus locais, controla disponibilidade, fotos, reservas recebidas e acompanha métricas no dashboard.
- **Administrador**: supervisiona o funcionamento geral da plataforma, aprovando anúncios e administrando os usuários.

Os casos de uso foram organizados dentro do limite do sistema (system boundary), evidenciando funcionalidades essenciais e destacando relações de inclusão, como:
- **Criar Reserva** «include» **Efetuar Pagamento**
- **Buscar Locais** «include» **Visualizar Local**

Este diagrama garante uma visão clara das funcionalidades que devem ser implementadas, servindo como referência para modelagem, regras de negócio, requisitos e priorização de desenvolvimento.

---

### 🖼️ Diagrama

<p align="center">
  <img width="1050" alt="Diagrama de Caso de Uso - LYSTA" src="https://github.com/user-attachments/assets/966c7acd-96ef-4bed-8e34-de359f1106d3">
</p>
