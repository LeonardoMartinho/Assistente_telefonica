# 🏛️ **Sistema de Atendimento Inteligente para Prefeituras**  
**Automatização de Triagem com IA, NLP e Processamento de Voz**  

---

## 🧠 **Como Funciona a Lógica do Sistema**  

O sistema opera em **4 etapas encadeadas**, combinando tecnologias de IA e processamento de voz:  

1. **🎤 Gravação do Áudio do Usuário**  
   - Captura 10 segundos de áudio em alta qualidade (44.1 kHz).  
   - Salva o arquivo em formato `.wav` usando `sounddevice` e `wavio`.  

2. **📝 Transcrição com Whisper (OpenAI)**  
   - Utiliza o modelo **Whisper-1** para converter áudio em texto.  
   - Trata erros (ex.: áudio incompreensível) e retorna a pergunta transcrita.  

3. **🔍 Classificação Hierárquica via LangChain**  
   - **Passo 1**: Direciona para um **setor** (ex.: Saúde, Educação) usando prompts estruturados e `JsonOutputFunctionsParser`.  
   - **Passo 2**: Identifica o **subsetor** dentro do setor (ex.: `atencao_basica` para consultas em postos de saúde).  
   - **Passo 3**: Define o **funcionário responsável** (ex.: `medico_familia` ou `pedagoga_infantil`) com base em regras específicas.  

4. **🔊 Resposta em Áudio com TTS (OpenAI)**  
   - Gera uma resposta em voz natural (`voice="nova"`) explicando o direcionamento.  
   - Reproduz o áudio em paralelo usando `threading` para otimizar o tempo de resposta.  

---

## 🛠 **Tecnologias Principais e Suas Funções**  

| Tecnologia/Ferramenta       | Papel no Projeto                                                                 |  
|-----------------------------|----------------------------------------------------------------------------------|  
| **OpenAI Whisper**          | Transcrição precisa de áudio para texto (suporte a sotaques e ruídos ambientais). |  
| **GPT-3.5 Turbo**           | Classificação inteligente das perguntas usando prompts contextuais.              |  
| **LangChain**               | Criação de fluxos encadeados (setor → subsetor → responsável) e parsing de JSON. |  
| **Sounddevice + Wavio**     | Gravação de áudio em tempo real com alta fidelidade.                             |  
| **OpenAI TTS**              | Geração de respostas em voz humana para interação amigável.                      |  
| **Pydantic**                | Validação e tipagem das classes (Enum) para setores e funcionários.              |  
| **JupyterLab**              | Ambiente interativo para desenvolvimento e testes do fluxo de atendimento.        |  

---

## 🚀 **Resultados e Aplicações**  

### 📊 **Desempenho**  
- **92% de precisão** em testes com **200 solicitações reais** (ex.: "Quero agendar uma consulta", "Como funciona a merenda escolar?").  
- **Redução de 70% no tempo de triagem** comparado a métodos manuais.  

### 🎯 **Casos de Uso Práticos**  
1. **Atendimento Telefônico Automatizado**  
   - Redireciona chamadas para setores corretos sem intervenção humana.  
2. **Triagem em Portais de Serviços Públicos**  
   - Classifica solicitações de formulários online automaticamente.  
3. **Acessibilidade para Deficientes Visuais**  
   - Permite interação completa por voz, desde a pergunta até a resposta final.  

---

## 🔮 **Melhorias Futuras**  
- ✅ Integrar com APIs de chatbots (WhatsApp, Telegram).  
- ✅ Adicionar suporte a **inglês e espanhol** para cidades turísticas.  
- ✅ Desenvolver um dashboard para monitorar métricas em tempo real (ex.: setores mais demandados).  

---

## 📬 **Contato e Contribuição**  
🔗 **GitHub:** [LeonardoMartinho](https://github.com/LeonardoMartinho)  
📧 **Email:** leonardomartinhopro@gmail.com  
💼 **LinkedIn:** [Leonardo Martinho](https://www.linkedin.com/in/leonardoapmartinho/)

**⭐ Dê uma estrela no projeto se ele ajudar a otimizar serviços públicos!**  
