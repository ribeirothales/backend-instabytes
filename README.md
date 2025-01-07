# 📸 InstaBytes API

Bem-vindo ao **InstaBytes**, uma API desenvolvida em Node.js que simula uma aplicação no estilo Instagram. A API oferece suporte para criar e gerenciar posts, fazer upload de imagens, e atualizar imagens já enviadas. Além disso, utiliza o **Google Gemini** para gerar descrições automáticas das imagens postadas, proporcionando uma experiência inovadora. 🌟

---

## ⚙️ Funcionalidades

- 📃 **Listar posts**: Exibe todos os posts cadastrados na aplicação.
- ➕ **Criar post**: Permite criar novos posts com título e descrição.
- 📤 **Upload de imagens**: Permite fazer o upload de imagens associadas aos posts.
- ✏️ **Atualizar post com IA**: Utiliza o **Google Gemini** para gerar descrições inteligentes e detalhadas das imagens postadas.
- 🌐 **Conexão em nuvem**: Hospedagem e banco de dados totalmente integrados ao Google Cloud e MongoDB Atlas.

---

## 🛠️ Tecnologias Utilizadas

- 🟡 **JavaScript**: Linguagem de programação utilizada no desenvolvimento da aplicação.
- 🟢 **Node.js**: Plataforma de execução do JavaScript no servidor.
- 🗄️ **MongoDB**: Banco de dados não relacional para armazenar informações dos posts.
- ☁️ **MongoDB Atlas**: Serviço em nuvem para hospedagem do banco de dados MongoDB.
- 🤖 **Google Gemini**: Ferramenta para geração automática de descrições das imagens postadas.
- 🌐 **Google Cloud**: Plataforma de hospedagem da aplicação.
---

## 🔗 Rotas Disponíveis

### 📃 1. Listar Todos os Posts
- **Descrição**: Retorna uma lista com todos os posts cadastrados.
- **Método**: `GET`
- **Endpoint**: `/posts`

### ➕ 2. Criar um Novo Post
- **Descrição**: Cria um novo post.  
- **Método**: `POST`
- **Endpoint**: `/posts`
- **Exemplo de requisição:**

```json
{
    "descricao": "Gato fazendo Post",
    "imgUrl": "https://placecats.com/millie/300/150",
    "alt": "Gato fazendo Post"   
}
```

### 📤 3. Fazer Upload de uma Imagem

- **Descrição**: Faz o upload de uma imagem.  
- **Método**: `POST`
- **Endpoint**: `/posts/upload`
- **Header**: `Content-Type: multipart/form-data`

### ✏️ 4. Atualizar uma Imagem

- **Descrição**: Atualiza a imagem de um post existente e utiliza o **Google Gemini** para gerar automaticamente uma descrição baseada no conteúdo da nova imagem.  O `id` deve ser substituído pelo identificador do post.  
- **Método**: `PUT`
- **Endpoint**: `/posts/upload/:id`

---

## ⚙️ Configuração do Projeto

### 📝 Pré-requisitos
- 🟡 **JavaScript** habilitado no ambiente de desenvolvimento.
- 🟢 **Node.js** instalado (v20 ou superior de preferência).
- 🗄️ Conta no **MongoDB Atlas**.
- ☁️ Conta no **Google Cloud** e acesso ao **Google Gemini**.

### 🟢 Instalação do Node.js
1. 🌐 Acesse o site oficial do Node.js: [https://nodejs.org/](https://nodejs.org/).  
2. 📥 Baixe a versão recomendada para o seu sistema operacional.  
3. 🖥️ Instale o Node.js seguindo os passos do instalador.  
4. ✅ Verifique a instalação no terminal:  
    ```bash
    node -v
    npm -v
    ```
### 🗄️ Configuração do MongoDB Atlas

1. 🌐 **Acesse o MongoDB Atlas**  
   - Vá para [MongoDB Atlas](https://www.mongodb.com/cloud/atlas) e crie uma conta, caso ainda não tenha.

2. ➕ **Crie um Cluster**  
   - Clique em **Create a Cluster** e siga os passos recomendados.  
   - Escolha a região mais próxima para melhor desempenho.

3. 📂 **Configure uma Database e Collection**  
   - Acesse o cluster criado e vá para **Database** > **Browse Collections**.  
   - Clique em **Add My Own Data** e insira:  
     - **Database Name**: `instabytes`  
     - **Collection Name**: `posts`

4. 🔑 **Gere a String de Conexão**  
   - Vá em **Database Access** e crie um usuário com permissões de leitura e escrita.  
   - Em **Network Access**, adicione o IP global (`0.0.0.0/0`) ou especifique os IPs confiáveis.  
   - Copie a **string de conexão** fornecida, no formato:  
     ```
     mongodb+srv://<username>:<password>@cluster0.mongodb.net/?retryWrites=true&w=majority
     ```
   - Substitua `<username>` e `<password>` pelos dados do usuário criado.  

5. 🔗 **Integração com a Aplicação**  
   - Insira a string de conexão no arquivo `.env` do projeto:  
     ```env
     MONGO_URI=mongodb+srv://<username>:<password>@cluster0.mongodb.net/instabytes?retryWrites=true&w=majority
     ```

### 🚀 Como Executar Localmente

1. 🖥️ Clone este repositório:

```bash
git clone https://github.com/joschonarth/instabytes-server.git
cd instabytes-server
```

2. 📦 Instale as dependências:

```bash
npm install
```

3. 🔑 Configure as variáveis de ambiente no arquivo `.env`:

```bash
STRING_CONEXAO = sua-conexao-do-mongo-atlas
GEMINI_API_KEY = sua-chave-api-do-google-gemini
```

4. ▶️ Inicie o servidor:

```bash
npm run dev
```

5. 🌐 Acesse a API em [http://localhost:3000](http://localhost:3000).

---

## 🌐 Frontend do Projeto

O código do frontend para a aplicação **InstaBytes** pode ser encontrado em um repositório separado. Este repositório contém a interface que consome a API desenvolvida no backend, permitindo a interação com os posts e o upload de imagens.

- **Repositório Frontend**: [InstaBytes Frontend - GitHub](https://github.com/joschonarth/instabytes-web)

---

## 📚 Documentações e Links Importantes

Aqui estão alguns links úteis para ajudar no desenvolvimento e configuração do projeto:

- 🟢 **Node.js**  
  [Site Oficial](https://nodejs.org/) | [Documentação](https://nodejs.org/en/docs/)

- 📦 **npm (Node Package Manager)**  
  [Site Oficial](https://www.npmjs.com/) | [Documentação](https://docs.npmjs.com/)

- 🗄️ **MongoDB**  
  [Site Oficial](https://www.mongodb.com/) | [Documentação](https://www.mongodb.com/docs/)

- ☁️ **MongoDB Atlas**  
  [Site Oficial](https://www.mongodb.com/cloud/atlas) | [Guia de Introdução](https://www.mongodb.com/docs/atlas/getting-started/)

- 🖼️ **Google Gemini**  
  [Página Oficial](https://gemini.google.com/app) | [Gemini API](https://ai.google.dev/gemini-api/docs)

- 🌐 **Google Cloud**  
  [Site Oficial](https://cloud.google.com/) | [Documentação](https://cloud.google.com/docs)

---

## 🤝 Contribuição

🙌 Sinta-se à vontade para contribuir com melhorias para o projeto. Faça um fork, crie uma nova branch para suas alterações e envie um pull request.

## 📞 Contato

<div>
    <a href="https://www.linkedin.com/in/ribeirothales/" target="_blank"><img src="https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white" target="_blank"></a>
    <a href="mailto:thales.o.ribeiro@gmail.com" target="_blank"><img src="https://img.shields.io/badge/Gmail-D14836?style=for-the-badge&logo=gmail&logoColor=white" target="_blank"></a>
</div>
