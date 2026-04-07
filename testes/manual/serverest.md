# Teste Manual – Cadastro e Login no Serverest

## 1️⃣ Objetivo

Verificar se o sistema **Serverest.dev** permite que um usuário **se cadastre e faça login corretamente**, garantindo que os dados são validados e a funcionalidade está operando conforme esperado.

---

## 2️⃣ Pré-condições

1. Ter acesso à internet.
2. Acessar o site [Serverest](https://serverest.dev/).
3. Ferramentas: navegador (Chrome, Firefox, Edge), planilha ou bloco de notas para registro de resultados.
4. Para o teste de login, o usuário deve estar previamente cadastrado.

---

## 3️⃣ Cenários de Teste

### 3.1 Cadastro de Usuário

| Passo | Ação                                    | Entrada de Dados                                    | Resultado Esperado                                                |
| ----- | --------------------------------------- | --------------------------------------------------- | ----------------------------------------------------------------- |
| 1     | Acessar a página de cadastro            | URL de cadastro no Serverest                        | Página de cadastro carregada com campos: nome, email, senha, etc. |
| 2     | Preencher o campo “Nome”                | Hora do QA                                       | Campo preenchido corretamente                                     |
| 3     | Preencher o campo “Email”               | [horadoqa@teste.com](mailto:horadoqa@teste.com) | Campo preenchido com email válido                                 |
| 4     | Preencher o campo “Senha”               | Senha123!                                           | Campo preenchido com senha válida                                 |
| 5     | Confirmar senha (se houver)             | Senha123!                                           | Campo preenchido corretamente                                     |
| 6     | Clicar em “Cadastrar”                   | -                                                   | Usuário cadastrado com sucesso, mensagem de confirmação exibida   |
| 7     | Tentar cadastrar com email já existente | [horadoqa@teste.com](mailto:horadoqa@teste.com) | Sistema retorna erro: “Email já cadastrado”                       |

💡 **Dica prática:** Anote qualquer mensagem de erro inesperada e capture prints da tela.

---

### 3.2 Login de Usuário

| Passo | Ação                                  | Entrada de Dados                                                  | Resultado Esperado                                                         |
| ----- | ------------------------------------- | ----------------------------------------------------------------- | -------------------------------------------------------------------------- |
| 1     | Acessar a página de login             | URL de login no Serverest                                         | Página de login carregada com campos: email, senha                         |
| 2     | Preencher o campo “Email”             | [horadoqa@teste.com](mailto:horadoqa@teste.com)               | Campo preenchido corretamente                                              |
| 3     | Preencher o campo “Senha”             | Senha123!                                                         | Campo preenchido corretamente                                              |
| 4     | Clicar em “Entrar”                    | -                                                                 | Usuário logado com sucesso, redirecionado para dashboard ou página inicial |
| 5     | Tentar login com senha incorreta      | [horadoqa@teste.com](mailto:horadoqa@teste.com) / SenhaErrada | Sistema retorna mensagem de erro: “Email ou senha incorretos”              |
| 6     | Tentar login com email não cadastrado | [horadoqa@naoexiste.com](mailto:horadoqa@naoexiste.com) / Senha123!     | Sistema retorna mensagem de erro: “Email não encontrado”                   |

💡 **Dica prática:** Teste também campos em branco para verificar validação: sistema deve impedir login sem email ou senha.

---

## 4️⃣ Observações

1. Registre todas as **mensagens de erro**, capturas de tela e comportamentos inesperados.
2. Caso algo falhe, detalhar passo, dados usados e resultado obtido.
3. Este teste pode ser repetido em diferentes navegadores para validar compatibilidade.
4. Após cadastro e login bem-sucedidos, tente realizar logout para verificar consistência do fluxo.

---

