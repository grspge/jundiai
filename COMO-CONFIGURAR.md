# Como configurar o app

Siga esses passos uma única vez. Leva cerca de 10 minutos.

---

## Passo 1 — Criar o projeto no Firebase

1. Acesse **https://console.firebase.google.com**
2. Clique em **"Criar um projeto"**
3. Dê um nome (ex: `meus-lugares-jundiai`)
4. Pode desativar o Google Analytics (não precisa)
5. Clique em **"Criar projeto"**

---

## Passo 2 — Criar o banco de dados

1. No menu lateral, clique em **"Realtime Database"**
2. Clique em **"Criar banco de dados"**
3. Escolha a localização **us-central1** (padrão)
4. Selecione **"Iniciar no modo de teste"** → clique em **Ativar**

> O modo de teste permite leitura/escrita sem login por 30 dias.
> Depois desse prazo, vá em "Regras" e cole isso para deixar permanente:
> ```json
> {
>   "rules": {
>     ".read": true,
>     ".write": true
>   }
> }
> ```

---

## Passo 3 — Pegar a configuração do Firebase

1. No menu lateral, clique na **engrenagem ⚙️** > **Configurações do projeto**
2. Role para baixo até **"Seus apps"**
3. Clique em **"</>  Web"** para registrar um app web
4. Dê qualquer apelido (ex: `lugares-web`) → clique em **Registrar app**
5. Você verá um bloco como este:

```js
const firebaseConfig = {
  apiKey: "AIzaSy...",
  authDomain: "meu-projeto.firebaseapp.com",
  databaseURL: "https://meu-projeto-default-rtdb.firebaseio.com",
  projectId: "meu-projeto",
  storageBucket: "meu-projeto.appspot.com",
  messagingSenderId: "123456789",
  appId: "1:123456789:web:abc123"
};
```

6. **Copie esse bloco inteiro.**

---

## Passo 4 — Colar a config no arquivo index.html

1. Abra o arquivo `index.html` em qualquer editor de texto (Bloco de Notas, VS Code, etc.)
2. Encontre esta linha:
   ```js
   const FIREBASE_CONFIG = "COLE_AQUI_SUA_CONFIG";
   ```
3. Substitua essa linha inteira pelo bloco que você copiou:
   ```js
   const firebaseConfig = {
     apiKey: "AIzaSy...",
     ...
   };
   ```
4. **Atenção:** mude `const firebaseConfig` para `const FIREBASE_CONFIG`:
   ```js
   const FIREBASE_CONFIG = {
     apiKey: "AIzaSy...",
     ...
   };
   ```
5. Salve o arquivo.

---

## Passo 5 — Publicar no GitHub Pages

1. Acesse **https://github.com** e faça login
2. Clique em **"New repository"** (botão verde)
3. Dê o nome `meus-lugares` (ou qualquer outro)
4. Deixe como **Public** → clique em **"Create repository"**
5. Na tela seguinte, clique em **"uploading an existing file"**
6. Arraste os dois arquivos: `index.html` e `COMO-CONFIGURAR.md`
7. Clique em **"Commit changes"**
8. Vá em **Settings** (aba do repositório) → **Pages** (menu lateral)
9. Em "Branch", selecione **main** → clique em **Save**
10. Aguarde 1-2 minutos. O link do seu app aparecerá ali, no formato:
    ```
    https://SEU-USUARIO.github.io/meus-lugares/
    ```

---

## Passo 6 — Compartilhar com a família

Basta enviar o link `https://SEU-USUARIO.github.io/meus-lugares/` para quem quiser.

Qualquer pessoa com o link pode ver e adicionar lugares. Os dados ficam sincronizados em tempo real para todos.

---

## Dúvidas frequentes

**Os dados somem se eu fechar o navegador?**
Não. Os dados ficam no Firebase, na nuvem. Fechou e abriu, tudo lá.

**Precisa criar conta para usar?**
Não. Qualquer pessoa com o link acessa direto.

**É gratuito para sempre?**
Sim. O plano Spark do Firebase é gratuito e o limite é generoso para uso pessoal (1 GB de armazenamento, 10 GB de transferência/mês). Uma lista de lugares nunca vai chegar perto disso.
