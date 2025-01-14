# Bot Telegram - Funcionalidades Avançadas

Este projeto é um bot do Telegram construído com a biblioteca `python-telegram-bot`. O bot oferece diversas funcionalidades, como pesquisa no Google, integração com o modelo generativo Gemini, tradução automática e interação em grupos. Além disso, o projeto conta com suporte a Docker para facilitar a implantação.

## Funcionalidades

1. **Pesquisa no Google**\
   O bot realiza pesquisas no Google utilizando a API Custom Search do Google. Retorna os resultados relevantes diretamente no chat.

2. **Interação em Grupos**

   - Obtém os membros do grupo (apenas administradores).
   - Retorna o ID do grupo onde o comando foi executado.

3. **Mensagem Automática**\
   Responde automaticamente a uma mensagem específica com uma saudação personalizada.

4. **Modelo Generativo (Gemini)**\
   Integração com o modelo generativo Gemini para gerar respostas baseadas em texto. O texto gerado é traduzido automaticamente para português antes de ser enviado ao usuário.

## Pré-requisitos

- **Python 3.9+**
- Bibliotecas instaladas via `pip`:
  - `python-telegram-bot`
  - `requests`
  - `python-dotenv`
  - `deep-translator`
  - `google.generativeai`

## Instalação

### Utilizando Ambiente Local

1. Clone este repositório:

   ```bash
   git clone https://github.com/seu_usuario/seu_repositorio.git
   cd seu_repositorio
   ```

2. Crie e ative um ambiente virtual:

   ```bash
   python -m venv venv
   source venv/bin/activate  # Para Linux/Mac
   venv\Scripts\activate     # Para Windows
   ```

3. Instale as dependências:

   ```bash
   pip install -r requirements.txt
   ```

4. Configure o arquivo `.env`:
   Crie um arquivo `.env` na raiz do projeto com as seguintes variáveis:

   ```
   TOKEN_API=<Seu_Token_Telegram>
   TARGET_CHAT_ID=<ID_Chat_Destino>
   CHAT_GROUP_ID=<ID_Grupo>
   SEARCH_ENGINE_ID=<ID_Mecanismo_Pesquisa>
   API_KEY=<Sua_Chave_API_Google>
   GEMINI_API_KEY=<Sua_Chave_API_Gemini>
   ```

5. Inicie o bot localmente:

   ```bash
   python desenvolvimentos.py
   ```

### Utilizando Docker

1. Certifique-se de que o Docker e o Docker Compose estejam instalados em sua máquina.

2. Clone este repositório:

   ```bash
   git clone https://github.com/seu_usuario/seu_repositorio.git
   cd seu_repositorio
   ```

3. Configure o arquivo `.env` conforme descrito anteriormente.

4. Construa e inicie o contêiner usando o Docker Compose:

   ```bash
   docker-compose up --build -d
   ```

O bot estará em execução no contêiner nomeado `bot-telegram`.

## Como Usar

1. **Inicie o Bot**\
   Caso esteja utilizando Docker, o bot já estará rodando após o comando `docker-compose up`. Caso contrário, siga os passos para inicialização no ambiente local.

2. **Comandos Disponíveis**

   - `/members` - Lista os membros administradores do grupo.
   - `/chatid` - Retorna o ID do grupo.
   - `/search <consulta>` - Realiza uma pesquisa no Google.
   - `/gemini <consulta>` - Gera conteúdo usando o modelo Gemini e traduz para português.

3. **Mensagem Automática**\
   Envie uma mensagem específica como "Manda oi pro Rafael" para receber uma resposta automática.

## Observações

- Certifique-se de que as APIs do Google e Gemini estão ativas em seu projeto na Google Cloud Console.
- O bot precisa das permissões necessárias para funcionar corretamente em grupos.
- Ao utilizar Docker, as variáveis de ambiente são automaticamente carregadas a partir do arquivo `.env`.

## Contribuição

Sinta-se à vontade para contribuir com melhorias ou novas funcionalidades! Faça um fork deste repositório, implemente suas mudanças e envie um pull request. 😊

---

### Licença

Este projeto é distribuído sob a licença MIT. Veja o arquivo [LICENSE](LICENSE) para mais detalhes. Os arquivos Dockerfile e docker-compose.yml também estão cobertos por esta licença.

