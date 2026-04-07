# Teste Automatizado – Cadastro e Login no Serverest (Playwright + JavaScript)

## 1️⃣ Objetivo

Automatizar a verificação de cadastro e login no Serverest.dev para garantir que as funcionalidades funcionem corretamente de forma repetitiva e confiável.

---

## 2️⃣ Pré-requisitos

1. Node.js versão 20.
2. Projeto com **Playwright** instalado:

```bash
npm init -y
npm install -D @playwright/test
```

3. Criar estrutura de pastas, por exemplo:

```
/tests
  cadastro-login.spec.js
/playwright.config.js
```

4. Navegador de teste: Chromium (padrão do Playwright).

---

## 3️⃣ Cenários de Teste

### 3.1 Cadastro de Usuário

**Script de exemplo (JavaScript + Playwright):**

```javascript
const { test, expect } = require('@playwright/test');

test.describe('Cadastro de usuário', () => {

  test('Deve cadastrar um usuário com sucesso', async ({ page }) => {
    await page.goto('https://serverest.dev/cadastro'); // URL de cadastro

    // Preencher campos
    await page.fill('input[name="nome"]', 'Hora do QA');
    await page.fill('input[name="email"]', 'horadoqa@teste.com');
    await page.fill('input[name="senha"]', 'Senha123!');

    // Submeter formulário
    await page.click('button[type="submit"]');

    // Verificar mensagem de sucesso
    const mensagem = await page.locator('.mensagem-sucesso').textContent();
    expect(mensagem).toContain('usuário cadastrado com sucesso');
  });

  test('Não deve cadastrar usuário com email existente', async ({ page }) => {
    await page.goto('https://serverest.dev/cadastro');

    await page.fill('input[name="nome"]', 'Hora do QA');
    await page.fill('input[name="email"]', 'horadoqa@teste.com');
    await page.fill('input[name="senha"]', 'Senha123!');
    await page.click('button[type="submit"]');

    const mensagemErro = await page.locator('.mensagem-erro').textContent();
    expect(mensagemErro).toContain('Email já cadastrado');
  });

});
```

---

### 3.2 Login de Usuário

**Script de exemplo:**

```javascript
test.describe('Login de usuário', () => {

  test('Deve logar com usuário cadastrado', async ({ page }) => {
    await page.goto('https://serverest.dev/login');

    await page.fill('input[name="email"]', 'horadoqa@teste.com');
    await page.fill('input[name="senha"]', 'Senha123!');
    await page.click('button[type="submit"]');

    const url = page.url();
    expect(url).toContain('/dashboard'); // ou a página inicial do usuário
  });

  test('Não deve logar com senha incorreta', async ({ page }) => {
    await page.goto('https://serverest.dev/login');

    await page.fill('input[name="email"]', 'horadoqa@teste.com');
    await page.fill('input[name="senha"]', 'SenhaErrada');
    await page.click('button[type="submit"]');

    const mensagemErro = await page.locator('.mensagem-erro').textContent();
    expect(mensagemErro).toContain('Email ou senha incorretos');
  });

  test('Não deve logar com email não cadastrado', async ({ page }) => {
    await page.goto('https://serverest.dev/login');

    await page.fill('input[name="email"]', 'teste@naoexiste.com');
    await page.fill('input[name="senha"]', 'Senha123!');
    await page.click('button[type="submit"]');

    const mensagemErro = await page.locator('.mensagem-erro').textContent();
    expect(mensagemErro).toContain('Email não encontrado');
  });

});
```

---

## 4️⃣ Observações

1. O seletor de mensagens (`.mensagem-sucesso`, `.mensagem-erro`) deve ser ajustado conforme a implementação real do Serverest.dev.
2. Para reexecutar os testes repetidamente, considere **resetar a base de dados** ou usar emails diferentes em cada execução.
3. É recomendado executar os testes em **modo headless** ou visual para depuração:

```bash
npx playwright test --headed
```

4. Capture screenshots em caso de falha para análise futura:

```javascript
await page.screenshot({ path: 'screenshots/falha_login.png' });
```

---

## Próximos passos:

Criar um teste incluindo **dados de teste variáveis, screenshots automáticas e relatório de execução**
