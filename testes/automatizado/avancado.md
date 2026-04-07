# Projeto de Teste Automatizado – Serverest.dev (Playwright + JavaScript)

## 1️⃣ Estrutura de Pastas

```
/serverest-tests
  /tests
    cadastro-login.spec.js
  /screenshots
  playwright.config.js
package.json
```

---

## 2️⃣ Configuração do Playwright

**playwright.config.js**

```javascript
// Configuração do Playwright
const { defineConfig } = require('@playwright/test');

module.exports = defineConfig({
  testDir: './tests',
  timeout: 30000,
  use: {
    headless: false,            // executar com UI para depuração
    screenshot: 'only-on-failure', // capturar screenshot em falhas
    video: 'retain-on-failure', // gravar vídeo em falhas
    trace: 'on-first-retry',    // rastreio para depuração
  },
  reporter: [['list'], ['html', { outputFolder: 'reports', open: 'never' }]], // relatório HTML
});
```

---

## 3️⃣ Teste Automatizado – Cadastro e Login

**tests/cadastro-login.spec.js**

```javascript
const { test, expect } = require('@playwright/test');

// Dados de teste
const usuarios = [
  { nome: 'Hora do QA', email: 'horadoqa@teste.com', senha: 'Senha123!' },
  { nome: 'QA Alternativo', email: 'qaalt@teste.com', senha: 'Senha123!' },
];

test.describe('Cadastro e Login Serverest', () => {

  test('Cadastro de usuário - sucesso', async ({ page }) => {
    await page.goto('https://serverest.dev/cadastro');

    const user = usuarios[0];
    await page.fill('input[name="nome"]', user.nome);
    await page.fill('input[name="email"]', user.email);
    await page.fill('input[name="senha"]', user.senha);
    await page.click('button[type="submit"]');

    const mensagem = await page.locator('.mensagem-sucesso').textContent();
    expect(mensagem).toContain('usuário cadastrado com sucesso');
  });

  test('Cadastro com email existente - falha', async ({ page }) => {
    await page.goto('https://serverest.dev/cadastro');

    const user = usuarios[0];
    await page.fill('input[name="nome"]', user.nome);
    await page.fill('input[name="email"]', user.email);
    await page.fill('input[name="senha"]', user.senha);
    await page.click('button[type="submit"]');

    const mensagemErro = await page.locator('.mensagem-erro').textContent();
    expect(mensagemErro).toContain('Email já cadastrado');
  });

  test('Login com usuário cadastrado - sucesso', async ({ page }) => {
    await page.goto('https://serverest.dev/login');

    const user = usuarios[0];
    await page.fill('input[name="email"]', user.email);
    await page.fill('input[name="senha"]', user.senha);
    await page.click('button[type="submit"]');

    await expect(page).toHaveURL(/dashboard/);
  });

  test('Login com senha incorreta - falha', async ({ page }) => {
    await page.goto('https://serverest.dev/login');

    const user = usuarios[0];
    await page.fill('input[name="email"]', user.email);
    await page.fill('input[name="senha"]', 'SenhaErrada');
    await page.click('button[type="submit"]');

    const mensagemErro = await page.locator('.mensagem-erro').textContent();
    expect(mensagemErro).toContain('Email ou senha incorretos');
  });

  test('Login com email não cadastrado - falha', async ({ page }) => {
    await page.goto('https://serverest.dev/login');

    await page.fill('input[name="email"]', 'naoexiste@teste.com');
    await page.fill('input[name="senha"]', 'Senha123!');
    await page.click('button[type="submit"]');

    const mensagemErro = await page.locator('.mensagem-erro').textContent();
    expect(mensagemErro).toContain('Email não encontrado');
  });

});
```

---

## 4️⃣ Como Executar

1. Instalar dependências:

```bash
npm install
npx playwright install
```

2. Executar todos os testes:

```bash
npx playwright test
```

3. Gerar relatório HTML:

```bash
npx playwright show-report
```

4. As screenshots e vídeos de falha serão salvos automaticamente em `/screenshots` e `/playwright-report`.

---

## 5️⃣ Observações Importantes

1. **Seletores**: `.mensagem-sucesso` e `.mensagem-erro` devem ser ajustados se a aplicação mudar.
2. **Base de dados**: Para testes repetitivos, é recomendado limpar dados ou usar emails diferentes.
3. **Reusabilidade**: O array `usuarios` permite adicionar facilmente novos dados de teste.
4. **Depuração**: Rode `headless: false` para ver o fluxo do teste no navegador.

---

## Próximo passo:

Criar **uma versão ainda mais completa**, incluindo **testes de logout, fluxo completo de cadastro+login+logout**, com **funções reutilizáveis** para tornar o código **modular e escalável**, ideal para projetos de QA maiores.

