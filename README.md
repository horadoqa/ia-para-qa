# 🤖 IA para QA

Muitas pessoas me perguntam: **“Por onde começar na área de Qualidade de Software?”**
Essa dúvida é mais comum do que parece, e pensando nisso, decidi transformar esse questionamento em um projeto que une teoria e prática de forma realista, aproveitando para introduzir o conhecimento em ferramentas modernas de Inteligência Artificial.

A ideia aqui é justamente “juntar o útil ao agradável”: oferecer um caminho estruturado para quem deseja entrar na área, sem perder a praticidade e a aplicabilidade imediata, tornando o aprendizado mais acessível e interessante para o momento atual.

## Como utilizar IA no QA ?

Antes de mais nada, saber o que precisamos na área de Qualidade de Software. 

Podemos começar explorando a área de QA usando uma [IA](./docs/ia.md) fazendo a primeira pergunta em um [chatbot](https://chatgpt.com/) usando um [prompt](./docs/prompt.md):


```
Por onde começar na área e Qualidade de Software ?
```

<details>
<summary>💡 Veja um exemplo de resposta</summary>

Começar na área de Qualidade de Software (QA) é uma ótima escolha — tem bastante demanda e várias portas de entrada. Vou te dar um caminho direto, sem enrolação, pra você sair do zero e começar bem:

---

## 📌 1. Entenda o que é Qualidade de Software

QA não é só “testar”. Envolve garantir que o software funcione bem, tenha boa experiência e não quebre.

Você vai lidar com:

* Encontrar bugs 🐞
* Garantir requisitos
* Melhorar processos
* Automatizar testes

---

## 📚 2. Aprenda os fundamentos

Antes de qualquer ferramenta, foque no básico:

* Tipos de teste:

  * Teste manual
  * Teste automatizado
  * Teste funcional
  * Teste de regressão

* Conceitos importantes:

  * Casos de teste
  * Plano de teste
  * Critérios de aceitação

* Metodologias:

  * Scrum / Kanban (ágeis)

👉 Pesquise também sobre **Engenharia de Software**, porque QA faz parte disso.

---

## 🛠️ 3. Comece com testes manuais (porta de entrada)

Essa é a forma mais rápida de entrar na área.

Você pode praticar assim:

* Testar sites e apps do dia a dia
* Criar casos de teste em planilhas
* Reportar bugs (como se estivesse numa empresa)

Ferramentas simples:

* Excel / Google Sheets
* Jira (muito usado no mercado)

---

## 💻 4. Aprenda automação (diferencial forte)

Depois do básico, vá pra automação — isso aumenta muito seu salário.

Comece com:

* Lógica de programação
* Uma linguagem:

  * JavaScript ou Python

Ferramentas populares:

* Selenium
* Cypress
* Playwright
* Robot Framework

---

## 🔄 5. Aprenda sobre APIs (muito importante)

Hoje QA não testa só interface.

Você precisa entender:

* REST APIs
* JSON
* Requisições HTTP

Ferramentas:

* Postman

---

## 📁 6. Monte um portfólio (isso é o que te contrata)

Mesmo sem experiência, você pode mostrar prática:

Inclua:

* Casos de teste
* Relatórios de bugs
* Testes automatizados (GitHub)

---

## 🎯 7. Primeiro emprego: o que buscar

Procure por vagas como:

* QA Júnior
* Testador de Software
* Analista de Testes

---

## 🚀 Dica importante (que muita gente ignora)

Não espere “estar pronto”.
Com 1–3 meses de estudo focado, já dá pra começar a aplicar.

</details>

---

## Agora que já que entendemos o que é Qualidade de Software vamos começar pelo básico.

### Tipos de teste:

<details>
<summary>✅ O que é Teste Manual ?</summary>

O **Teste Manual** é o processo de verificar se um software funciona corretamente **sem o uso de ferramentas automáticas**. Ou seja, o testador executa cenários de teste **passo a passo**, observa o comportamento do sistema e registra se ele está funcionando conforme o esperado.

### Principais características:

1. **Interação humana**: O testador utiliza o software como um usuário real faria.
2. **Cenários de teste**: São scripts ou listas de ações que devem ser seguidas para validar funcionalidades.
3. **Registro de resultados**: O testador documenta erros (bugs) encontrados e confirma funcionalidades corretas.
4. **Flexibilidade**: Permite identificar problemas que testes automatizados podem não perceber, como usabilidade ou experiência do usuário.

### Exemplos de Teste Manual:

* Clicar em botões e menus para garantir que eles funcionam.
* Preencher formulários e verificar se os dados são salvos corretamente.
* Testar diferentes fluxos de um aplicativo, como login, cadastro, compra, etc.

---

</details>

<details>
<summary>✅ O que é Teste Automatizado ?</summary>

O **Teste Automatizado** é o processo de testar o software **usando ferramentas e scripts**, em vez de fazer tudo manualmente. O objetivo é **executar testes repetitivos de forma rápida e confiável**, liberando o testador para tarefas mais complexas ou criativas.

### Principais características:

1. **Execução por script**: O teste é programado usando linguagens como **Python, Java, JavaScript** ou ferramentas de automação.
2. **Repetição fácil**: Um mesmo teste pode ser executado várias vezes sem esforço adicional.
3. **Detecção rápida de erros**: Útil para regressão, testes de performance e grandes sistemas.
4. **Integração com CI/CD**: Pode ser conectado a pipelines de desenvolvimento para testar automaticamente a cada atualização do software.

### Exemplos de Teste Automatizado:

* Testar se o login funciona corretamente em várias combinações de usuário e senha.
* Verificar se uma página web carrega corretamente após mudanças no código.
* Simular milhares de usuários acessando um sistema para medir performance.

### Ferramentas populares:

* **Selenium** – automação de testes web.
* **Cypress** – automação moderna de testes web.
* **Appium** – automação de aplicativos móveis.
* **JUnit / TestNG** – frameworks de teste para Java.

💡 **Dica**: Para começar, é interessante dominar **teste manual primeiro**. Ele te ensina a entender como o software funciona e quais cenários testar. Depois, você aprende automação para **executar testes mais rapidamente e em maior escala**.

---

</details>

<details>
<summary>✅ O que é Teste Funcional ?</summary>

O **Teste Funcional** é um tipo de teste de software que verifica se o sistema **cumpre corretamente todas as funcionalidades esperadas**. Ele responde à pergunta:

> “O software faz **o que deveria fazer**?”

Ou seja, o foco está **nas ações e resultados do sistema**, e não na forma como ele foi implementado.

### Principais características:

1. **Baseado em requisitos**: O teste é feito a partir de especificações ou histórias de usuário.
2. **Orientado a entradas e saídas**: Você fornece dados ao sistema e verifica se o resultado está correto.
3. **Não se preocupa com o código interno**: Diferente do teste estrutural (ou teste de caixa branca), que analisa a lógica interna.

### Exemplos de Teste Funcional:

* Verificar se um botão “Cadastrar” salva corretamente os dados do usuário.
* Testar se um sistema de pagamento processa transações corretamente.
* Conferir se filtros de busca em um site retornam os resultados certos.

### Relação com outros tipos de teste:

* Pode ser feito **manual ou automatizado**.
* Engloba **testes de regressão**, **testes de integração** e **testes de interface** quando focados nas funcionalidades.

💡 Dica prática: sempre que você pensar em teste funcional, imagine que você é **o usuário**: você testa se o software faz o que você espera que ele faça, sem se preocupar com como ele faz.

---

</details>

<details>
<summary>✅ O que é Teste Regressivo ?</summary>

O **Teste Regressivo** é um tipo de teste que verifica se **uma mudança recente no software (como uma correção de bug, nova funcionalidade ou atualização) não quebrou funcionalidades que já estavam funcionando antes**.

Em outras palavras, ele garante que o sistema **continua funcionando corretamente após alterações**.

### Principais características:

1. **Baseado em funcionalidades existentes**: Testa recursos que já funcionavam.
2. **Previne efeitos colaterais**: Mudanças em uma parte do sistema podem afetar outras partes.
3. **Pode ser manual ou automatizado**: Automatizar testes regressivos é muito comum porque eles são repetitivos.
4. **Crucial em ambientes de atualização contínua**: Por exemplo, em metodologias ágeis ou CI/CD.

### Exemplos de Teste Regressivo:

* Após corrigir um problema no login, testar novamente cadastro, recuperação de senha e perfil do usuário.
* Depois de adicionar uma nova funcionalidade de carrinho de compras, testar se o processo de pagamento ainda funciona.
* Atualização de versão de um sistema de ERP, garantindo que relatórios antigos continuam corretos.

💡 **Dica prática:**
Pense no teste regressivo como **uma “rede de segurança”**: ele garante que novas mudanças não causem efeitos inesperados em partes já testadas do sistema.

</details>

---

### Conceitos importantes:

<details>
<summary>✅ O que é um Caso de Teste ?</summary>

Um **Caso de Teste (Test Case)** é um **documento ou conjunto de instruções que descreve uma situação específica a ser testada** em um software. Ele indica **o que testar, como testar e qual resultado é esperado**.

Em outras palavras, é o roteiro que o testador segue para verificar se o sistema está funcionando corretamente.

### Principais componentes de um Caso de Teste:

1. **ID ou código** – identificador único do caso de teste.
2. **Descrição** – resumo do que será testado.
3. **Pré-condições** – o que precisa estar configurado ou disponível antes do teste.
4. **Passos** – instruções detalhadas do que o testador deve fazer.
5. **Entrada de dados** – informações que serão inseridas no sistema.
6. **Resultado esperado** – qual deve ser o comportamento correto do sistema.
7. **Resultado obtido** – preenchido após o teste, indicando sucesso ou falha.
8. **Status / Observações** – registro de erros ou detalhes adicionais.

### Exemplo de Caso de Teste Simples:

* **ID:** CT001
* **Descrição:** Testar login com usuário válido.
* **Pré-condição:** Usuário já cadastrado no sistema.
* **Passos:**

  1. Abrir a página de login.
  2. Inserir usuário e senha válidos.
  3. Clicar no botão “Entrar”.
* **Entrada de dados:** Usuário: joao123 | Senha: 12345
* **Resultado esperado:** O sistema redireciona para a página principal do usuário.
* **Resultado obtido:** [Preencher após teste]
* **Status:** [Passou/Falhou]

💡 **Dica prática:**
Casos de teste bem escritos ajudam a **garantir que nada importante seja esquecido** e servem de base para **testes manuais ou automáticos**.

---

</details>

<details>
<summary>✅ O que é um Plano de Teste ?</summary>

O **Plano de Teste** é um **documento que descreve toda a estratégia e abordagem para testar um software**. Ele serve como um guia para a equipe de QA sobre **o que será testado, como será testado, por quem e quando**.

Enquanto um **Caso de Teste** é um roteiro específico para testar uma função, o **Plano de Teste** é o planejamento completo do processo de testes.

---

### Principais componentes de um Plano de Teste:

1. **Objetivo do teste:** Por que o teste está sendo feito (ex.: garantir que a nova funcionalidade não quebre o sistema).
2. **Escopo do teste:** Quais funcionalidades ou módulos serão testados e quais não serão.
3. **Tipos de teste:** Funcional, regressivo, desempenho, segurança etc.
4. **Critérios de entrada e saída:** Quando o teste pode começar e quais condições definem que ele terminou.
5. **Recursos necessários:** Equipe, ambiente, ferramentas, dados de teste.
6. **Cronograma:** Datas e ordem dos testes.
7. **Riscos e dependências:** Possíveis problemas que podem afetar o teste.
8. **Critérios de aceitação:** O que define que o software passou nos testes.

---

### Diferença entre Plano de Teste e Caso de Teste:

| Aspecto     | Plano de Teste                          | Caso de Teste                          |
| ----------- | --------------------------------------- | -------------------------------------- |
| Propósito   | Definir **estratégia geral**            | Definir **passo a passo de um teste**  |
| Abrangência | Todo o projeto/sistema                  | Funcionalidade específica              |
| Conteúdo    | Objetivos, escopo, recursos, cronograma | Passos, entradas, resultados esperados |
| Detalhe     | Mais estratégico                        | Mais operacional                       |

💡 **Dica prática:**
O Plano de Teste é essencial para **organizar e documentar todo o processo de QA**, principalmente em projetos grandes. Ele garante que ninguém esqueça funcionalidades importantes e ajuda a controlar prazos e recursos.

</details>

---

<details>
<summary>✅ O que são Critérios de aceitação ?</summary>

Os **Critérios de Aceitação** são **condições específicas que um produto ou funcionalidade deve cumprir para ser considerado pronto ou aprovado**. Eles ajudam a definir **o que significa “feito”** do ponto de vista do usuário ou do negócio.

Em outras palavras, são regras que dizem:

> “Para que esta funcionalidade seja considerada correta, ela precisa se comportar assim…”

---

### Principais características:

1. **Baseados em requisitos ou histórias de usuário**: Normalmente extraídos do backlog em metodologias ágeis.
2. **Claros e objetivos**: Devem ser fáceis de verificar e mensurar.
3. **Servem como base para testes**: Orientam a criação de casos de teste e testes de aceitação.
4. **Foco no valor para o usuário**: O critério diz se a funcionalidade entrega o que o usuário precisa.

---

### Exemplos de Critérios de Aceitação:

**Exemplo 1 – Login de usuário:**

* O usuário deve conseguir fazer login com e-mail e senha válidos.
* Mensagem de erro deve ser exibida se o usuário digitar senha incorreta.
* O sistema deve redirecionar para a página principal após login bem-sucedido.

**Exemplo 2 – Carrinho de compras:**

* O usuário deve conseguir adicionar e remover produtos do carrinho.
* O total do carrinho deve atualizar corretamente a cada alteração.
* Produtos esgotados não podem ser adicionados.

💡 **Dica prática:**
Critérios de aceitação são como uma **checklist oficial de aprovação**. Tudo que está listado deve ser cumprido para que a funcionalidade seja considerada concluída e liberada para o usuário.

</details>

---

### Metodologias Ágeis:

<details>
<summary>✅ O que é Scrum ?</summary>

O **Scrum** é uma **metodologia ágil** para gerenciamento de projetos, especialmente usada em **desenvolvimento de software**. Ele ajuda equipes a entregar produtos de forma **incremental e iterativa**, focando na colaboração, adaptação e entrega contínua de valor.

Em vez de planejar tudo de uma vez, o Scrum organiza o trabalho em **pequenos ciclos chamados Sprints**, normalmente de **1 a 4 semanas**.

---

### Principais pilares do Scrum:

1. **Transparência** – Todos sabem o que está acontecendo no projeto.
2. **Inspeção** – O progresso é revisado regularmente.
3. **Adaptação** – Mudanças são incorporadas rapidamente com base em feedback.

---

### Papéis principais no Scrum:

1. **Product Owner (PO)** – Representa o cliente; define prioridades e requisitos do produto.
2. **Scrum Master** – Facilita o processo, remove obstáculos e garante que a equipe siga o Scrum.
3. **Equipe de Desenvolvimento / QA** – Desenvolvedores e testadores que constroem e testam o software.

---

### Artefatos principais:

* **Product Backlog** – Lista priorizada de funcionalidades e requisitos do produto.
* **Sprint Backlog** – Lista de tarefas selecionadas para a Sprint atual.
* **Incremento** – Produto funcionando ao final da Sprint, pronto para ser entregue.

---

### Eventos no Scrum:

1. **Sprint Planning** – Planejamento do que será feito na Sprint.
2. **Daily Scrum (Daily Stand-up)** – Reunião diária rápida para alinhamento.
3. **Sprint Review** – Apresentação do que foi entregue na Sprint.
4. **Sprint Retrospective** – Avaliação do processo para melhorar continuamente.

💡 **Dica prática:**
Para QA, o Scrum ajuda a **integrar os testes no ciclo de desenvolvimento**, permitindo testar funcionalidades assim que são implementadas e garantindo que a qualidade seja contínua, não apenas no final do projeto.

---

</details>

<details>
<summary>✅ O que é Kanban ?</summary>

O **Kanban** é uma **metodologia visual de gerenciamento de trabalho**, criada para **otimizar o fluxo de tarefas e reduzir gargalos**. Ele ajuda equipes a **visualizar, priorizar e acompanhar o progresso** das atividades em tempo real.

Enquanto o Scrum organiza o trabalho em Sprints (ciclos fixos), o Kanban é **contínuo**, permitindo que as tarefas avancem conforme a capacidade da equipe.

---

### Principais elementos do Kanban:

1. **Quadro Kanban (Board)** – Representa visualmente o fluxo de trabalho, normalmente com colunas como:

   * **A Fazer (To Do)**
   * **Em Progresso (In Progress)**
   * **Concluído (Done)**
2. **Cartões (Cards)** – Cada tarefa ou item de trabalho é representado por um cartão que se move pelas colunas.
3. **Limites de trabalho em andamento (WIP Limits)** – Define quantas tarefas podem estar em progresso ao mesmo tempo, evitando sobrecarga.
4. **Fluxo contínuo** – Não há Sprints fixos; as tarefas avançam conforme forem sendo concluídas.

---

### Benefícios do Kanban:

* Visibilidade total do fluxo de trabalho.
* Redução de gargalos e atrasos.
* Flexibilidade para lidar com mudanças rapidamente.
* Fácil de integrar com QA, pois testes podem ser visualizados e priorizados junto com desenvolvimento.

💡 **Dica prática:**
No QA, o Kanban é ótimo para **organizar casos de teste, bugs e melhorias**, garantindo que nada fique parado e que a equipe tenha clareza do que precisa ser testado ou corrigido.

---

</details>
