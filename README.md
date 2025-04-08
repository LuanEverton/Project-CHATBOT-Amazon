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

## 🔧 Instalação
Clone o repositório e instale as dependências:
```bash
# Clonar o repositório
git clone https://github.com/seu-usuario/bot-amazon-whatsapp.git
cd bot-amazon-whatsapp

# Criar ambiente virtual (opcional)
python -m venv venv
source venv/bin/activate  # Linux/macOS
venv\Scripts\activate  # Windows

# Instalar bibliotecas
pip install -r requirements.txt
```

Crie um arquivo `.env` com suas credenciais:
```env
AWS_ACCESS_KEY=SEU_ACCESS_KEY
AWS_SECRET_KEY=SEU_SECRET_KEY
ASSOCIATE_TAG=SEU_ASSOCIATE_TAG

TWILIO_SID=SEU_TWILIO_SID
TWILIO_AUTH_TOKEN=SEU_TWILIO_AUTH_TOKEN
TWILIO_WHATSAPP_NUMBER=whatsapp:+14155238886
WHATSAPP_GROUP_NUMBER=whatsapp:+SEU_NUMERO

OPENAI_API_KEY=SUA_OPENAI_API_KEY
```

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




