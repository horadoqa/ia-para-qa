# Teste Funcional – Cadastro e Login no Serverest.dev

## 1️⃣ Objetivo

O **Teste Funcional** tem como objetivo verificar se o **cadastro e o login de usuários** estão funcionando conforme os requisitos, garantindo que o sistema faça **o que deveria fazer** do ponto de vista do usuário final.

> Este teste pode ser realizado **manual ou automatizado**.

---

## 2️⃣ Pré-condições

1. Acessar a internet e o site [Serverest.dev](https://serverest.dev/).
2. Para cadastro: usar um email que **ainda não esteja cadastrado**.

   * Exemplo: `horadoqa@teste.com`
3. Para login: ter um usuário **previamente cadastrado**.
4. Ferramentas: navegador web, planilha ou sistema para registro de resultados.

---

## 3️⃣ Cenários de Teste Funcional

### 3.1 Cadastro de Usuário

| Passo | Ação                                                  | Dados                                                                                              | Resultado Esperado                                      | Status | Observações |
| ----- | ----------------------------------------------------- | -------------------------------------------------------------------------------------------------- | ------------------------------------------------------- | ------ | ----------- |
| 1     | Abrir página de cadastro                              | -                                                                                                  | Página de cadastro carregada corretamente               | ☐      |             |
| 2     | Preencher campos obrigatórios                         | Nome: Hora do QA <br> Email: [horadoqa@teste.com](mailto:horadoqa@teste.com) <br> Senha: Senha123! | Campos preenchidos corretamente                         | ☐      |             |
| 3     | Clicar em “Cadastrar”                                 | -                                                                                                  | Sistema exibe mensagem “Usuário cadastrado com sucesso” | ☐      |             |
| 4     | Tentar cadastrar com email já existente               | [horadoqa@teste.com](mailto:horadoqa@teste.com)                                                    | Sistema exibe mensagem de erro “Email já cadastrado”    | ☐      |             |
| 5     | Validar que dados obrigatórios não podem ficar vazios | Nome / Email / Senha vazios                                                                        | Sistema impede cadastro e exibe mensagens de validação  | ☐      |             |

---

### 3.2 Login de Usuário

| Passo | Ação                                   | Dados                                                         | Resultado Esperado                                      | Status | Observações |
| ----- | -------------------------------------- | ------------------------------------------------------------- | ------------------------------------------------------- | ------ | ----------- |
| 1     | Abrir página de login                  | -                                                             | Página de login carregada corretamente                  | ☐      |             |
| 2     | Preencher email e senha válidos        | [horadoqa@teste.com](mailto:horadoqa@teste.com) / Senha123!   | Usuário loga com sucesso e é redirecionado ao dashboard | ☐      |             |
| 3     | Login com senha incorreta              | [horadoqa@teste.com](mailto:horadoqa@teste.com) / SenhaErrada | Sistema exibe mensagem “Email ou senha incorretos”      | ☐      |             |
| 4     | Login com email não cadastrado         | [naoexiste@teste.com](mailto:naoexiste@teste.com) / Senha123! | Sistema exibe mensagem “Email não encontrado”           | ☐      |             |
| 5     | Testar comportamento com campos vazios | Email / Senha vazios                                          | Sistema impede login e exibe mensagem de validação      | ☐      |             |

---

## 4️⃣ Critérios de Aceitação

* ✅ Cadastro só é permitido se todos os campos obrigatórios estiverem preenchidos corretamente.
* ✅ Mensagens de erro devem aparecer de forma clara e específica para cada falha.
* ✅ Login só funciona para usuários previamente cadastrados com senha correta.
* ✅ Sistema deve redirecionar para a página correta após login bem-sucedido.
* ✅ Qualquer falha deve ser registrada com **print ou observação detalhada**.

---

## 5️⃣ Observações

1. **Manual ou automatizado:**

   * Manual: ideal para validação rápida ou quando a automação ainda não está implementada.
   * Automatizado: ideal para regressão contínua e execução repetitiva.

2. **Boa prática:**

   * Testar diferentes combinações de dados para validar regras de negócio (ex.: emails inválidos, senhas fracas).
   * Registrar **mensagens de erro e comportamentos inesperados**.

3. **Reusabilidade:**

   * Este teste funcional pode ser integrado em um checklist de QA ou em scripts automatizados.

---
