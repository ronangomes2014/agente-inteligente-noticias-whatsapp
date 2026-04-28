# agente-inteligente-noticias-whatsapp
🤖 Agente inteligente de notícias que utiliza n8n, Twilio, webhook e RSS do Bing para entregar resumos personalizados via WhatsApp. Inclui integração com ngrok para webhooks locais.
Este projeto é um bot de automação para WhatsApp que coleta dados do usuário (Nome, Cidade, Assunto) e realiza uma busca em tempo real pelas notícias mais recentes, entregando um resumo formatado com títulos em negrito, numeração e links.

## 🚀 Tecnologias Utilizadas
* **[n8n](https://n8n.io/)**: Ferramenta de automação baseada em nós para orquestrar o fluxo.
* **[ngrok](https://ngrok.com/)**: Para criar um túnel seguro e expor o webhook local do n8n para a internet.
* **Twilio Sandbox for WhatsApp**: Para o envio e recebimento de mensagens.
* **RSS Bing News**: Fonte de dados para as notícias.

## 🛠️ Como Funciona
1. O usuário inicia a conversa via WhatsApp.
2. O bot solicita os dados (Nome, Cidade, Assunto) separados por vírgula.
3. O n8n processa a entrada, faz o "split" dos dados e consulta o RSS do Bing.
4. As notícias são formatadas, numeradas e enviadas de volta ao usuário, respeitando o limite de caracteres do WhatsApp.

## 📋 Pré-requisitos
Para rodar este fluxo, você precisará de:
* Instância do **n8n** (Local ou Cloud).
* Uma conta na **Twilio** (Configurar o WhatsApp Sandbox).
* **ngrok** instalado para expor seu webhook se estiver rodando localmente.

> **Nota importante:** Este repositório contém o arquivo JSON do workflow n8n. As credenciais da Twilio (Account SID e Auth Token) **não estão incluídas** e devem ser configuradas pelo usuário final diretamente no n8n.

## 🔧 Instalação
1. Clone este repositório.
2. No seu n8n, clique em **Import from File** e selecione o arquivo `.json` deste projeto.
3. Configure suas credenciais da Twilio no nó de mensagens.
4. Execute o **ngrok** na porta do seu n8n (ex: `ngrok http 5678`).
5. Copie a URL do ngrok e cole nas configurações de Sandbox da Twilio (campo *When a message comes in*).
