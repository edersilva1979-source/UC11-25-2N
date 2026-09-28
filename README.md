# UC11-25-2N

# 🧪 Testes e Melhorias em Aplicações

Repositório desenvolvido para as aulas da Unidade Curricular de Testes e Melhorias em Aplicações.

Durante o curso, nós vamos aprender desde os conceitos básicos de testes de software até a criação de testes automatizados utilizando TypeScript e Jest.

A proposta é aprender de forma prática, entendendo não apenas como criar um teste, mas principalmente por que devemos testar nossos sistemas.

Ao longo das aulas, vamos desenvolver pequenos projetos, testar regras de negócio, trabalhar com APIs, utilizar mocks e spies e aplicar boas práticas utilizadas no desenvolvimento de software.

---

# 🎯 Objetivos do Curso

Ao final das aulas, nós deveremos ser capazes de:

* compreender o que são testes de software
* entender a importância dos testes durante o desenvolvimento
* identificar diferentes tipos de testes
* criar testes unitários
* utilizar Jest com TypeScript
* testar regras de negócio
* testar situações de sucesso e erro
* criar e testar APIs
* realizar testes de integração
* utilizar Supertest
* trabalhar com mocks e spies
* isolar dependências
* aplicar o padrão AAA
* identificar falhas em aplicações
* realizar melhorias no código
* organizar testes de forma profissional

---

# 🛠️ Tecnologias Utilizadas

Durante o curso utilizaremos:

* TypeScript
* Node.js
* Jest
* Express
* Supertest
* Visual Studio Code
* Postman
* Git
* GitHub

---

# 📚 Estrutura do Curso

O curso está organizado em 12 aulas de aproximadamente 3 horas cada.

Carga horária total aproximada:

**36 horas**

---

# 🎮 Aula 01 | Introdução aos Testes de Software

Nesta primeira aula vamos entender por que os testes existem e qual é sua importância no desenvolvimento de sistemas.

### Conteúdos

* O que é teste de software
* Por que testar
* Erro, defeito e falha
* Qualidade de software
* Teste manual
* Teste automatizado
* Exemplos de falhas em sistemas
* Importância dos testes durante o desenvolvimento

### Missão

🐞 Identificar possíveis falhas em um sistema.

---

# 🎮 Aula 02 | Tipos e Níveis de Testes

Vamos conhecer diferentes formas de testar uma aplicação.

### Conteúdos

* Teste unitário
* Teste de integração
* Teste funcional
* Teste de sistema
* Teste de regressão
* Teste de aceitação
* Cenários de teste
* Resultado esperado e resultado obtido

### Missão

🔎 Escolher o tipo de teste adequado para diferentes situações.

---

# 🎮 Aula 03 | Preparando TypeScript e Jest

Nesta aula começamos a automação dos testes.

### Conteúdos

* Criação do projeto Node.js
* Instalação do TypeScript
* Instalação do Jest
* Configuração do ts jest
* Estrutura do projeto
* Primeiro arquivo TypeScript
* Primeiro teste automatizado

### Exemplo

```ts
export function somar(a: number, b: number): number {
  return a + b;
}
```

Teste:

```ts
expect(somar(2, 3)).toBe(5);
```

### Missão

⚙️ Fazer o primeiro teste passar.

---

# 🎮 Aula 04 | Testes Unitários com Jest

Agora começamos a explorar melhor o Jest.

### Conteúdos

* describe
* it
* test
* expect
* toBe
* toEqual
* toBeTruthy
* toBeFalsy
* toThrow

### Estrutura básica

```ts
describe('Calculadora', () => {

  it('deve somar dois números', () => {

    const resultado = somar(10, 5);

    expect(resultado).toBe(15);

  });

});
```

### Missão

🧪 Criar testes para diferentes funções.

---

# 🎮 Aula 05 | Testando Regras de Negócio

Nesta etapa vamos sair dos exemplos básicos e testar regras mais próximas de sistemas reais.

### Conteúdos

* Validação de dados
* Condições
* Cenários de sucesso
* Cenários de erro
* Casos limites
* Organização dos testes

### Exemplo

```ts
export function calcularPreco(valor: number): number {

  const temDesconto = valor > 100;

  return temDesconto ? valor * 0.9 : valor;

}
```

### Missão

💰 Garantir que as regras de negócio funcionem corretamente.

---

# 🎮 Aula 06 | Organização e Boas Práticas

Nesta aula vamos melhorar a qualidade dos nossos testes.

### Conteúdos

* Organização dos arquivos
* Nomeação dos testes
* Testes independentes
* Testes pequenos
* Evitar duplicação
* Preparação de cenários
* Introdução ao padrão AAA

### Padrão AAA

AAA significa:

```text
Arrange
Act
Assert
```

Podemos entender como:

```text
Preparar
Executar
Validar
```

### Missão

🧹 Transformar testes difíceis de entender em testes organizados.

---

# 🎮 Aula 07 | Criando uma API com TypeScript

Nesta aula vamos criar uma API para posteriormente realizar testes nela.

### Estrutura

```text
src
│
├── controllers
│
├── routes
│
├── services
│
├── types
│
├── app.ts
└── server.ts
```

### Rotas utilizadas

```text
POST /users
GET /users
GET /users/:id
```

### Conteúdos

* Conceito de API
* HTTP
* Request
* Response
* JSON
* Rotas
* Controllers
* Services
* Interfaces
* Express

### Missão

🌐 Colocar nossa primeira API em funcionamento.

---

# 🎮 Aula 08 | Testando o UserService

Com nossa API criada, começaremos a testar suas regras de negócio.

### Conteúdos

* Testes do UserService
* Cadastro de usuário
* Validação de nome
* Validação de email
* Email duplicado
* Busca por ID
* Listagem de usuários
* Testes de exceções

### Missão

👤 Garantir que usuários inválidos não entrem no sistema.

---

# 🎮 Aula 09 | Testes de Integração com Supertest

Agora vamos testar a API realizando requisições HTTP.

### Conteúdos

* Introdução ao Supertest
* Testando endpoints
* POST
* GET
* Body
* Status HTTP
* JSON
* Testes de sucesso
* Testes de erro

### Exemplo

```ts
const response = await request(app)
  .post('/users')
  .send({
    name: 'Maria',
    email: 'maria@email.com'
  });

expect(response.status).toBe(201);
```

### Missão

📡 Testar a comunicação real entre as partes da API.

---

# 🎮 Aula 10 | Mocks e Spies

Nem sempre queremos utilizar uma dependência real durante nossos testes.

Nesta aula aprenderemos a controlar essas dependências.

### Conteúdos

* O que é dependência
* Isolamento de dependências
* Mock
* Spy
* jest.fn()
* jest.spyOn()
* mockReturnValue()
* toHaveBeenCalled()
* toHaveBeenCalledWith()
* not.toHaveBeenCalled()

### Mock

O mock substitui uma dependência por um comportamento controlado.

```ts
const mockTransportadora = {
  enviar: jest.fn().mockReturnValue(true)
};
```

### Spy

O spy permite observar chamadas realizadas a determinado método.

```ts
const spy = jest.spyOn(
  transportadoraService,
  'enviar'
);
```

### Missão

🛡️ Isolar uma dependência externa sem prejudicar nossos testes.

---

# 🎮 Aula 11 | Testes com Padrões Profissionais

Nesta aula vamos revisar nossos testes pensando na organização utilizada em projetos profissionais.

### Checklist

* O teste possui objetivo claro?
* O nome explica o comportamento esperado?
* O teste é independente?
* Existe cenário de sucesso?
* Existem cenários de erro?
* Os casos limites foram considerados?
* Dependências externas foram isoladas?
* O padrão AAA foi aplicado?
* O teste pode ser executado várias vezes?
* O resultado é previsível?

### Missão

✅ Fazer uma revisão de qualidade nos testes desenvolvidos.

---

# 🎮 Aula 12 | Projeto Final

## Operação Logística

Na última aula teremos uma missão final.

Uma empresa de logística precisa validar seu sistema de processamento de envios antes de colocá lo em produção.

O sistema deverá considerar:

* peso do pacote
* CEP
* cálculo do frete
* aprovação da transportadora
* erros de processamento

### Regras

Peso máximo:

```text
50 kg
```

Frete para pacotes até 10 kg:

```text
R$ 20,00
```

Frete para pacotes acima de 10 kg:

```text
R$ 40,00
```

### O aluno deverá

* criar testes unitários
* testar situações de sucesso
* testar situações de erro
* utilizar mocks
* utilizar spies
* validar chamadas
* aplicar AAA
* manter os testes independentes

### Missão Final

🚚 Garantir que o sistema esteja preparado para entrar em produção.

---

# 🧪 Executando os Testes

Depois de baixar o projeto:

```bash
npm install
```

Para executar os testes:

```bash
npm test
```

Para acompanhar os testes durante o desenvolvimento:

```bash
npm run test:watch
```

Quando configurada a cobertura:

```bash
npm run test:coverage
```

---

# 📁 Organização Sugerida

```text
testes-software
│
├── src
│   ├── controllers
│   ├── routes
│   ├── services
│   ├── types
│   ├── app.ts
│   └── server.ts
│
├── tests
│   ├── unit
│   └── integration
│
├── package.json
├── tsconfig.json
├── jest.config.js
└── README.md
```

---

# 🏆 Sistema de Missões

Durante o curso podemos tratar cada conteúdo como uma nova missão.

| Conquista | Objetivo |
| :--- | :--- |
| 🐞 Bug Hunter | Encontrar e testar uma falha |
| 🧪 Test Starter | Criar o primeiro teste |
| 🛡️ Mock Master | Isolar uma dependência |
| 👁️ Spy Expert | Monitorar uma chamada |
| 🧹 Clean Tester | Organizar testes com AAA |
| 🌐 API Tester | Testar endpoints |
| 🚀 Production Ready | Concluir o desafio final |

---

# 📝 Avaliação

A avaliação final será dividida em duas etapas.

### Parte teórica

5 questões de múltipla escolha sobre os principais conceitos estudados.

### Parte prática

Desenvolvimento de testes para um sistema de logística utilizando TypeScript e Jest.

Serão considerados:

* funcionamento dos testes
* cobertura dos cenários solicitados
* uso correto de mocks e spies
* aplicação do padrão AAA
* organização
* qualidade do código
* interpretação das regras de negócio

---

# 💡 Conceito Principal do Curso

> Testar não é desconfiar do código. É cuidar dele.

Nosso objetivo não é apenas escrever código que funciona.

Nosso objetivo é aprender a verificar, de maneira sistemática, se ele continua funcionando quando diferentes situações acontecem.

---

# 👨‍🏫 Professor

**Prof. Éder Silva**

Desenvolvimento de Sistemas

---

## 🎯 Missão do aluno

**Entregar qualidade, não apenas código.**
