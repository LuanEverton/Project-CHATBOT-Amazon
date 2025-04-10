# Bot de Promoções da Amazon para WhatsApp

## 📌 Sobre o Projeto
Este bot busca produtos em promoção na **Amazon** usando a **Product Advertising API** e envia ofertas automaticamente para um **grupo do WhatsApp** via **Twilio API**. Além disso, utiliza o **ChatGPT** para gerar mensagens personalizadas para cada categoria de produto.

---

## 🚀 Funcionalidades
✅ Buscar produtos em promoção na Amazon
✅ Filtrar os melhores descontos
✅ Gerar mensagens personalizadas com o ChatGPT
✅ Enviar as ofertas automaticamente para o WhatsApp

---

## 🛠️ Tecnologias Utilizadas
- **Python**
- **Amazon Product Advertising API** (para buscar promoções)
- **Twilio API** (para envio no WhatsApp)
- **OpenAI API (ChatGPT)** (para criar mensagens personalizadas)

---

## 📌 Pré-requisitos
Antes de rodar o projeto, você precisa configurar algumas credenciais:

1. **Amazon Product Advertising API**
   - Criar uma conta em [Amazon Associates](https://affiliate-program.amazon.com/)
   - Obter **Access Key**, **Secret Key** e **Associate Tag**

2. **Twilio API (WhatsApp)**
   - Criar conta em [Twilio](https://www.twilio.com/)
   - Obter **Account SID**, **Auth Token** e registrar um número autorizado

3. **OpenAI API (ChatGPT)**
   - Criar conta em [OpenAI](https://openai.com/)
   - Obter a **API Key**

---



## 🏗️ Algoritmo do Chatbot (Portugol)
```portugol
// Configuração das chaves de API
definir API_OPENAI como "SUA_OPENAI_API_KEY"
definir TWILIO_SID como "SEU_TWILIO_SID"
definir TWILIO_AUTH_TOKEN como "SEU_TWILIO_AUTH_TOKEN"
definir TWILIO_WHATSAPP_NUMBER como "whatsapp:+14155238886"
definir WHATSAPP_GROUP_NUMBER como "whatsapp:+SEU_NUMERO"

// Função para gerar mensagem promocional
funcao gerarMensagemPromocional(categoria, produto, desconto, link)
    definir prompt como "Crie uma mensagem criativa para uma promoção na categoria " + categoria + ". Produto: " + produto + ", Desconto: " + desconto + "%, Link: " + link
    chamar API do ChatGPT com prompt
    retornar resposta da API
fimfuncao

// Função para enviar mensagem no WhatsApp
funcao enviarMensagemWhatsApp(mensagem)
    definir cliente como novo Cliente(TWILIO_SID, TWILIO_AUTH_TOKEN)
    definir msg como cliente.enviarMensagem(
        corpo = mensagem,
        de = TWILIO_WHATSAPP_NUMBER,
        para = WHATSAPP_GROUP_NUMBER
    )
fimfuncao

// Simulação de um produto
categoria <- "Eletrônicos"
produto <- "Fone de Ouvido Bluetooth"
desconto <- 30
link <- "https://www.amazon.com.br/produto-exemplo"

// Gera e envia mensagem
mensagemPromocional <- gerarMensagemPromocional(categoria, produto, desconto, link)
enviarMensagemWhatsApp(mensagemPromocional)

escrever("Mensagem enviada com sucesso!")
```

---

## 🎯 Como Executar o Bot
```bash
python bot.py
```

## 🤝 Contribuição
Sinta-se à vontade para contribuir! Faça um **fork**, crie uma **branch** e envie um **pull request**. 😃




