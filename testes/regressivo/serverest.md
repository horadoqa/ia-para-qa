# Teste Regressivo – Cadastro e Login no Serverest.dev

## 1️⃣ Objetivo

O **Teste Regressivo** verifica se alterações recentes no sistema **não afetaram funcionalidades que já estavam funcionando**, garantindo que o cadastro e login de usuários continuem operando corretamente.

> ⚠️ Pode ser realizado **manual** ou **automatizado**, dependendo do estágio do projeto e das ferramentas disponíveis.

---

## 2️⃣ Pré-condições

1. Acessar a internet e o site [Serverest.dev](https://serverest.dev/).
2. Ter dados de usuários previamente cadastrados.

   * Exemplo: `horadoqa@teste.com` / `Senha123!`
3. Para testes automatizados: Node.js e Playwright (ou outra ferramenta de automação) configurados.
4. Ferramentas para registro de resultado: planilha, bloco de notas ou sistema de testes.

---

## 3️⃣ Cenários de Teste

### 3.1 Teste Manual

| Passo | Ação                                 | Dados                                                                                                 | Resultado Esperado                                     |
| ----- | ------------------------------------ | ----------------------------------------------------------------------------------------------------- | ------------------------------------------------------ |
| 1     | Acessar a página de cadastro         | -                                                                                                     | Página de cadastro carregada                           |
| 2     | Preencher campos de um novo usuário  | Nome: QA Regressivo<br>Email: [regressivo@teste.com](mailto:regressivo@teste.com)<br>Senha: Senha123! | Campos preenchidos corretamente                        |
| 3     | Clicar em “Cadastrar”                | -                                                                                                     | Usuário cadastrado com sucesso, mensagem exibida       |
| 4     | Tentar cadastrar com email existente | [horadoqa@teste.com](mailto:horadoqa@teste.com)                                                       | Sistema retorna mensagem de erro “Email já cadastrado” |
| 5     | Acessar a página de login            | -                                                                                                     | Página de login carregada                              |
| 6     | Preencher email e senha válidos      | [horadoqa@teste.com](mailto:horadoqa@teste.com) / Senha123!                                           | Login bem-sucedido, redirecionamento para dashboard    |
| 7     | Login com senha incorreta            | [horadoqa@teste.com](mailto:horadoqa@teste.com) / SenhaErrada                                         | Sistema retorna erro “Email ou senha incorretos”       |
| 8     | Login com email não cadastrado       | [naoexiste@teste.com](mailto:naoexiste@teste.com) / Senha123!                                         | Sistema retorna erro “Email não encontrado”            |

💡 **Dica prática:** Registrar **mensagens de erro, prints da tela e qualquer comportamento inesperado**.

---

### 3.2 Teste Automatizado (Playwright + JavaScript)

**Exemplo de estrutura de teste regressivo:**

```javascript id="f2xwhq"
const { test, expect } = require('@playwright/test');

test.describe('Teste Regressivo – Cadastro e Login', () => {

  test('Cadastro existente deve falhar', async ({ page }) => {
    await page.goto('https://serverest.dev/cadastro');
    await page.fill('input[name="nome"]', 'Hora do QA');
    await page.fill('input[name="email"]', 'horadoqa@teste.com');
    await page.fill('input[name="senha"]', 'Senha123!');
    await page.click('button[type="submit"]');

    const mensagemErro = await page.locator('.mensagem-erro').textContent();
    expect(mensagemErro).toContain('Email já cadastrado');
  });

  test('Login com usuário válido deve funcionar', async ({ page }) => {
    await page.goto('https://serverest.dev/login');
    await page.fill('input[name="email"]', 'horadoqa@teste.com');
    await page.fill('input[name="senha"]', 'Senha123!');
    await page.click('button[type="submit"]');

    await expect(page).toHaveURL(/dashboard/);
  });

  test('Login com senha incorreta deve falhar', async ({ page }) => {
    await page.goto('https://serverest.dev/login');
    await page.fill('input[name="email"]', 'horadoqa@teste.com');
    await page.fill('input[name="senha"]', 'SenhaErrada');
    await page.click('button[type="submit"]');

    const mensagemErro = await page.locator('.mensagem-erro').textContent();
    expect(mensagemErro).toContain('Email ou senha incorretos');
  });

  test('Login com email não cadastrado deve falhar', async ({ page }) => {
    await page.goto('https://serverest.dev/login');
    await page.fill('input[name="email"]', 'naoexiste@teste.com');
    await page.fill('input[name="senha"]', 'Senha123!');
    await page.click('button[type="submit"]');

    const mensagemErro = await page.locator('.mensagem-erro').textContent();
    expect(mensagemErro).toContain('Email não encontrado');
  });

});
```

💡 **Dica prática:** Este teste deve ser **executado sempre que houver atualizações no cadastro ou login** para garantir que novas alterações não quebrem funcionalidades existentes.

---

## 4️⃣ Observações

1. **Manual ou automatizado:**

   * **Manual:** ideal para testes rápidos ou quando não há automação implementada.
   * **Automatizado:** ideal para regressão contínua, testes repetitivos e integração em pipelines CI/CD.

2. **Importância do teste regressivo:**

   * Garante que correções de bugs ou novas funcionalidades **não introduzam falhas em funcionalidades já existentes**.

3. **Boas práticas:**

   * Limpar ou isolar dados entre execuções.
   * Registrar prints, logs ou vídeos no caso de falhas.
   * Executar testes em múltiplos navegadores (Chrome, Firefox, Edge) para verificar compatibilidade.

---

Se você quiser, posso criar **uma versão de checklist pronta**, onde o testador **marca manualmente cada passo ou registra resultados automáticos**, pronta para uso em QA real e fácil de imprimir.

Quer que eu faça essa versão prática de checklist?
