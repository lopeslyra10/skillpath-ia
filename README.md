# 🎓 SkillPath IA 🤖📚

Projeto desenvolvido para a disciplina DISRUPTIVE ARCHITECTURES: IoT, IoB & Generative IA, com o objetivo de criar um sistema inteligente capaz de recomendar trilhas profissionais personalizadas utilizando IA Generativa (Gemini), Deep Learning, FastAPI, Oracle, Java Spring MVC, Ngrok e integração total entre diversas disciplinas.

# 📡 Descrição

O SkillPath IA é uma API inteligente que recebe perguntas dos usuários, processa dados extraídos do banco Oracle, utiliza o modelo Gemini 2.5 Flash para gerar recomendações personalizadas e envia automaticamente o histórico para o back-end em Java, onde a interação é armazenada no banco de dados.

A aplicação integra as seguintes tecnologias:

🧠 Gemini 2.5 Flash (Google GenAI)

⚡ FastAPI + Python (API de IA)

🌐 Ngrok para expor a API online

🗄 Banco Oracle (dataset exportado em JSON)

☕ Java Spring MVC para painel admin + registro do histórico

📱 Mobile (conceito) para consumo da IA

🔧 Dataset real do Oracle convertido para JSON

🔗 Integração entre Python → Java → Oracle

# 🔑 Novas implementações (Sprint Final – IA Integrada)

API FastAPI rodando no Google Colab com Uvicorn.

Integração completa com o modelo Gemini 2.5 Flash.

Exportação do banco Oracle em JSON para contextualização da IA.

Sistema de prompts otimizados (Prompt Engineering).

Envio automático do histórico IA → API Java.

Persistência em banco via tabela NS_IA_HISTORICO.

Exposição pública da API via Ngrok.

Interface móvel (conceitual) consumindo a API .NET.

# 🔧 Tecnologias Utilizadas

🤖 Google GenAI - Gemini 2.5 Flash

⚡ FastAPI + Uvicorn

🧩 Python 3.12

🌐 Ngrok (HTTP)

🗄 Oracle Database

☕ Java Spring MVC (Histórico da IA)

🔄 Integração Python → Java → Oracle

🧪 JSON dataset baseado nas tabelas do SkillPath

🔐 Headers e comunicação segura entre APIs

#📲 Funcionalidades

🔍 Recomendação de trilhas profissionais baseada em:

Área

Nível

Notas médias

Álvaro comportamental baseado nas avaliações

Padrões identificados via dataset

💬 Chat com IA generativa usando dados reais.

📨 Envio automático do histórico para a API Java:

Prompt enviado

Resposta gerada pela IA

Data/Hora

🗄 Armazenamento automático no Oracle.

# 📡 API exposta globalmente via ngrok, permitindo integração com:

Aplicativo Mobile

API .NET

Painel Admin Java

# 🛠️ Como usar
1. Clone o repositório
```git
git clone https://github.com/skillpath-project/skillpath-ia.git
```
2. Instale as dependências
```bash
!pip install pyngrok
!pip install google-genai
!pip install fastapi uvicorn nest_asyncio
```
3. Configure sua API KEY do Gemini
```python
os.environ["GOOGLE_API_KEY"] = userdata.get("GEMINI_API_KEY")
client = genai.Client()
```
4. Configure o Ngrok
```python
ngrok.set_auth_token("SEU_TOKEN_NGROK")
public_url = ngrok.connect(8000, "http")
print(public_url)
```
5. Execute a API FastAPI no Colab
```python
uvicorn_thread = threading.Thread(target=run_uvicorn_thread, args=(api,))
uvicorn_thread.start()
```
A API ficará disponível em:
https://SEU_NGROK.ngrok-free.app

# 🔌 Endpoints

GET /

Retorna o status:
```json
{ "status": "SkillPath IA funcionando!" }
```
POST /ask

Envia prompt ao modelo Gemini:

Request:
```json
{
  "prompt": "Recomende trilhas de Front-End"
}
```

Response:
```json
{
  "user_message": "Recomende trilhas de Front-End",
  "ia_response": "Texto gerado pelo Gemini baseado no dataset Oracle..."
}
```
🔗 Integração com Java – Histórico da IA

Toda interação é enviada automaticamente para:

POST http://localhost:8080/ia/historico/external


Payload enviado ao Java:
```json
{
  "prompt": "Recomende trilhas de front",
  "resposta": "Front-End React Developer - nível iniciante..."
}
```

Armazenado na tabela:

NS_IA_HISTORICO

# 🗄️ Dataset Oracle

O dataset é carregado automaticamente:
```python
with open("dataset_skillpath.json") as f:
    dataset_json = json.load(f)

```
Exemplo de entrada:
```json
{
  "id_usuario_final": 1,
  "nome_usuario": "Augusto",
  "id_trilha": 1,
  "nome_trilha": "Front-End React Developer",
  "nivel": "INICIANTE",
  "valor_nota": 5
}
```
# 🧪 Teste via chat interativo

No Colab:

Você: Recomende trilhas de front

```bash
SkillPath IA: Olá! Com certeza posso te ajudar a encontrar trilhas...
```
## Intergantes
Augusto Lopes Lyra — RM 558209

Felipe Ulson Sora — RM 555462

Vinícius Ribeiro Nery — RM 559165

## [▶️ Vídeo de Demonstração — SkillPath IA](https://youtu.be/VKHiXhAGfUU)
## [📄 Ver dataset_skillpath.json](./dataset_skillpath.json)



## 📅 Status do Projeto

🟢 Sprint Final: IA integrada e funcional</br>
🟢 API FastAPI + Gemini + Oracle JSON</br>
🟢 Histórico salvo no Java + Oracle</br>
🟢 API exposta via Ngrok</br>
🟢 Pronto para apresentação final

## 📌 Licença
Projeto acadêmico, desenvolvido exclusivamente para fins educacionais.
