# ✅ Checklist de Teste Regressivo – Serverest.dev

**Objetivo:** Garantir que o cadastro e login de usuários continuem funcionando após alterações no sistema.

**Pré-condições:**

* Usuário previamente cadastrado: `horadoqa@teste.com / Senha123!`
* Acessar [Serverest.dev](https://serverest.dev/)
* Ferramentas de registro: planilha, bloco de notas ou sistema de testes

---

## 1️⃣ Cadastro de Usuário

| Passo | Ação                                 | Dados                                                                                                     | Esperado                            | Status | Observações |
| ----- | ------------------------------------ | --------------------------------------------------------------------------------------------------------- | ----------------------------------- | ------ | ----------- |
| 1     | Abrir página de cadastro             | -                                                                                                         | Página carregada                    | ☐      |             |
| 2     | Preencher campos com novo usuário    | Nome: QA Regressivo <br> Email: [regressivo@teste.com](mailto:regressivo@teste.com) <br> Senha: Senha123! | Campos preenchidos corretamente     | ☐      |             |
| 3     | Clicar em “Cadastrar”                | -                                                                                                         | Usuário cadastrado com sucesso      | ☐      |             |
| 4     | Tentar cadastrar com email existente | [horadoqa@teste.com](mailto:horadoqa@teste.com)                                                           | Sistema exibe “Email já cadastrado” | ☐      |             |

---

## 2️⃣ Login de Usuário

| Passo | Ação                           | Dados                                                         | Esperado                                     | Status | Observações |
| ----- | ------------------------------ | ------------------------------------------------------------- | -------------------------------------------- | ------ | ----------- |
| 1     | Abrir página de login          | -                                                             | Página carregada                             | ☐      |             |
| 2     | Login com usuário válido       | [horadoqa@teste.com](mailto:horadoqa@teste.com) / Senha123!   | Redirecionado para dashboard                 | ☐      |             |
| 3     | Login com senha incorreta      | [horadoqa@teste.com](mailto:horadoqa@teste.com) / SenhaErrada | Mensagem de erro “Email ou senha incorretos” | ☐      |             |
| 4     | Login com email não cadastrado | [naoexiste@teste.com](mailto:naoexiste@teste.com) / Senha123! | Mensagem de erro “Email não encontrado”      | ☐      |             |

---

## 3️⃣ Observações Gerais

* ✅ **Registro de falhas:**

  * Para testes manuais, tire print da tela e registre na coluna “Observações”.
  * Para testes automatizados, grave vídeo ou screenshot em falhas.

* ✅ **Execução contínua:**

  * Este checklist deve ser utilizado sempre que houver **novas funcionalidades, correções de bugs ou alterações no sistema**.

* ✅ **Dados de teste:**

  * Para evitar conflitos, use emails diferentes a cada execução ou limpe os dados do banco se possível.

---

Próximos passos:

Criar **uma versão ainda mais avançada**, em **formato de planilha Excel/Google Sheets interativa**, com:

* ✅ Colunas de Status automatizadas
* ✅ Condição de Passou/Falhou
* ✅ Espaço para capturas de tela
* ✅ Links diretos para páginas de teste

Isso deixa o checklist pronto para **uso em equipe de QA profissional**.
