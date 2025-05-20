![image](https://github.com/user-attachments/assets/9a13b559-d7f7-497a-bcd3-84a3f704e948)# Lead Automation com n8n + IA
Projeto desenvolvido com foco em automação e integração de ferramentas utilizando o n8n, Google APIs e IA generativa.

## Objetivo
Automatizar o atendimento a um novo lead, realizando as seguintes etapas:

1. Validação de dados recebidos (e-mail e telefone).
2. Agendamento automático de reunião no Google Calendar.
3. Geração de mensagem personalizada com IA confirmando o agendamento.
4. Registro do lead em uma planilha do Google Sheets.
5. Simulação do envio da mensagem via Webhook (ex: WhatsApp).

## Uso de IA no fluxo
A inteligência artificial foi incorporada por meio do nó AI Transform do n8n.
A função principal foi gerar uma mensagem formal personalizada com base nos dados do lead.
### Prompt usado:
```text
Crie uma mensagem formal em português para {{nome}}, confirmando que a reunião foi agendada para {{dataFormatada}}.
```
- A data foi convertida usando `toLocaleString()` para facilitar a leitura.
- A IA foi utilizada de forma gratuita, sem depender da OpenAI ou uso de tokens pagos.

## Tecnologias & Ferramentas
- **n8n** – Workflows de automação
- **Google Calendar API** – Criação de eventos
- **Google Sheets API** – Registro de dados
- **Webhook.site** – Simulação de envio de mensagens
- **AI Transform (LLM)** – Geração de texto com IA
- **OAuth 2.0** – Autenticação com Google

## Visão Geral do Fluxo
![image](https://github.com/user-attachments/assets/bb9cffe0-3e00-4502-8685-1006b025e958)

## Como testar o fluxo

### 1. Importe o arquivo My_workflow.json no seu n8n.

### 2. Configure credenciais válidas para:

- Google Calendar

- Google Sheets

### 3. Simule o envio de um lead via Webhook (Postman ou outro).

### 4. Verifique:

- Evento criado no Google Calendar.

- Linha adicionada à planilha.

- Mensagem gerada pela IA enviada para o Webhook.

## Melhorias para Produção
- Integração real com WhatsApp (ex: Twilio API).
- Logs de erro e autenticação mais robusta.
- Integração com banco de dados relacional (ex: Supabase, PostgreSQL).
- Notificações internas para equipe de vendas em leads pendentes.
