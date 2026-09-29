# 🍔 Caso de Teste: Cadastro de Usuário do Delivery

## 📚 Objetivo da Atividade

Nesta atividade, nós vamos elaborar e analisar casos de teste para o cadastro de usuários de um sistema de delivery.

Nosso objetivo será verificar se as regras de negócio estão sendo respeitadas e identificar situações que possam provocar comportamentos incorretos no sistema.

Antes de automatizarmos os testes utilizando TypeScript e Jest, precisamos aprender a pensar nos cenários que deverão ser testados.

> Um bom teste não verifica apenas se o sistema funciona. Ele também tenta descobrir quando e como o sistema pode falhar.

---

# 🎯 Funcionalidade

Vamos considerar que nosso sistema de delivery possui um cadastro de usuários.

Cada usuário deverá possuir os seguintes campos:

| Campo      | Tipo sugerido | Obrigatório |
| :--------- | :------------ | :---------: |
| ID         | number        |     Sim     |
| Nome       | string        |     Sim     |
| Usuário    | string        |     Sim     |
| Senha      | string        |     Sim     |
| Observação | string        |     Não     |

Exemplo de um usuário válido:

```text
ID: 1
Nome: Maria Silva
Usuário: maria
Senha: 123456
Observação: Usuária do setor administrativo
```

---

# 📋 Regras de Negócio

Nosso cadastro deverá respeitar as seguintes regras:

1. O ID deve ser informado.
2. Não poderão existir dois usuários com o mesmo ID.
3. O Nome não poderá ficar em branco.
4. O Usuário não poderá ficar em branco.
5. Não poderão existir dois cadastros com o mesmo Usuário.
6. A Senha não poderá ficar em branco.
7. A Observação será opcional.
8. O cadastro somente será concluído quando todas as regras obrigatórias forem atendidas.

---

# 🧪 Casos de Teste

Vamos criar diferentes situações para verificar o comportamento do cadastro.

| Caso | Cenário                              | Dados utilizados                        | Resultado esperado          |
| :--- | :----------------------------------- | :-------------------------------------- | :-------------------------- |
| CT01 | Cadastro válido                      | 1, Maria Silva, maria, 123456, Entregas | Cadastro realizado          |
| CT02 | Cadastro sem observação              | 2, João Silva, joao, abc123, vazio      | Cadastro realizado          |
| CT03 | ID duplicado                         | ID já cadastrado                        | Erro: ID já cadastrado      |
| CT04 | Usuário duplicado                    | Usuário já cadastrado                   | Erro: Usuário já cadastrado |
| CT05 | Nome vazio                           | Nome vazio                              | Erro: Nome obrigatório      |
| CT06 | Usuário vazio                        | Usuário vazio                           | Erro: Usuário obrigatório   |
| CT07 | Senha vazia                          | Senha vazia                             | Erro: Senha obrigatória     |
| CT08 | ID não informado                     | ID ausente                              | Erro: ID obrigatório        |
| CT09 | Todos os campos obrigatórios vazios  | ID, Nome, Usuário e Senha vazios        | Cadastro não realizado      |
| CT10 | Nome somente com espaços             | Nome contendo apenas espaços            | Erro: Nome obrigatório      |
| CT11 | Usuário somente com espaços          | Usuário contendo apenas espaços         | Erro: Usuário obrigatório   |
| CT12 | Senha somente com espaços            | Senha contendo apenas espaços           | Erro: Senha obrigatória     |
| CT13 | Observação somente com espaços       | Observação contendo espaços             | Cadastro permitido          |
| CT14 | Nome com espaços internos            | Ana Maria Silva                         | Cadastro realizado          |
| CT15 | Usuário contendo números             | maria123                                | Cadastro realizado          |
| CT16 | Senha com letras e números           | Teste123                                | Cadastro realizado          |
| CT17 | Senha com caracteres especiais       | Teste@123                               | Cadastro realizado          |
| CT18 | Nome com acentos                     | José Antônio                            | Cadastro realizado          |
| CT19 | Usuário diferente com mesmo nome     | Maria Silva e usuário maria2            | Cadastro realizado          |
| CT20 | Mesmo usuário com outro ID           | ID diferente e usuário existente        | Erro: Usuário já cadastrado |
| CT21 | Mesmo ID com outro usuário           | ID existente e usuário diferente        | Erro: ID já cadastrado      |
| CT22 | ID igual a zero                      | ID = 0                                  | Verificar regra definida    |
| CT23 | ID negativo                          | ID menor que zero                       | Verificar regra definida    |
| CT24 | Cadastro depois de corrigir erro     | Corrigir os dados inválidos             | Cadastro realizado          |
| CT25 | Dois cadastros válidos consecutivos  | Dados completamente diferentes          | Ambos cadastrados           |
| CT26 | Usuário com letras maiúsculas        | maria e MARIA                           | Verificar regra definida    |
| CT27 | Usuário com espaços nas extremidades | espaço antes ou depois do usuário       | Verificar tratamento        |
| CT28 | Nome muito grande                    | Texto muito extenso                     | Verificar limite definido   |
| CT29 | Usuário muito grande                 | Texto muito extenso                     | Verificar limite definido   |
| CT30 | Senha muito grande                   | Texto muito extenso                     | Verificar limite definido   |

---

# 🔍 Teste de ID Duplicado

Vamos analisar o caso `CT03`.

## Pré condição

Já existe o seguinte usuário:

```text
ID: 10
Nome: Maria Silva
Usuário: maria
Senha: 123456
```

Agora tentaremos cadastrar:

```text
ID: 10
Nome: João Silva
Usuário: joao
Senha: abc123
```

Observe que os nomes e usuários são diferentes.

Porém, o ID é o mesmo.

## Resultado esperado

```text
Cadastro não realizado.
ID já cadastrado.
```

O sistema não deverá permitir o cadastro.

---

# 🔍 Teste de Usuário Duplicado

Vamos analisar o `CT04`.

Já existe:

```text
ID: 10
Nome: Maria Silva
Usuário: maria
Senha: 123456
```

Agora tentaremos:

```text
ID: 20
Nome: Maria Oliveira
Usuário: maria
Senha: abc123
```

O ID é diferente, porém o usuário:

```text
maria
```

já existe.

## Resultado esperado

```text
Cadastro não realizado.
Usuário já cadastrado.
```

---

# ⚠️ Testando Campos em Branco

Não devemos verificar apenas campos completamente vazios.

Por exemplo:

```text
Nome: ""
```

Também precisamos considerar:

```text
Nome: "     "
```

No segundo exemplo existem caracteres, mas todos são espaços.

Visualmente, para o usuário, o campo continua vazio.

Em TypeScript podemos utilizar:

```ts
if (!nome || nome.trim() === '') {
  throw new Error('Nome obrigatório');
}
```

O método `trim()` remove espaços existentes no início e no final do texto.

O mesmo conceito poderá ser aplicado aos demais campos conforme as regras definidas.

---

# 🧠 Requisitos Não Definidos

Durante os testes podemos encontrar situações que não foram especificadas nas regras de negócio.

Isso também faz parte do trabalho de teste de software.

Por exemplo:

## ID igual a zero

```text
ID: 0
```

Será permitido?

Precisamos definir.

---

## ID negativo

```text
ID: -10
```

Será permitido?

Precisamos definir.

---

## Diferença entre maiúsculas e minúsculas

Considere:

```text
maria
```

e:

```text
MARIA
```

São usuários diferentes?

Ou devem ser considerados o mesmo usuário?

A regra precisa ser definida antes de implementarmos o teste definitivo.

---

# 📊 Matriz de Decisão

Podemos visualizar algumas das principais regras desta forma:

| ID único | Nome preenchido | Usuário único | Senha preenchida | Resultado   |
| :------: | :-------------: | :-----------: | :--------------: | :---------- |
|   Sim    |       Sim       |      Sim      |       Sim        | ✅ Cadastrar |
|   Não    |       Sim       |      Sim      |       Sim        | ❌ Bloquear  |
|   Sim    |       Não       |      Sim      |       Sim        | ❌ Bloquear  |
|   Sim    |       Sim       |      Não      |       Sim        | ❌ Bloquear  |
|   Sim    |       Sim       |      Sim      |       Não        | ❌ Bloquear  |
|   Não    |       Não       |      Não      |       Não        | ❌ Bloquear  |

---

# 🧪 Categorias dos Testes

Para facilitar nossa organização, podemos separar os casos em grupos.

## ✅ Testes Positivos

São situações em que esperamos que o cadastro seja realizado.

```text
CT01
CT02
CT14
CT15
CT16
CT17
CT18
CT19
CT25
```

---

## ❌ Campos Obrigatórios

Verificam se o sistema impede dados obrigatórios ausentes.

```text
CT05
CT06
CT07
CT08
CT09
CT10
CT11
CT12
```

---

## 🔁 Duplicidades

Verificam as regras relacionadas ao ID e ao nome de usuário.

```text
CT03
CT04
CT20
CT21
```

---

## 📏 Limites e Dados Especiais

Verificam situações menos comuns.

```text
CT22
CT23
CT26
CT27
CT28
CT29
CT30
```

---

## 🔧 Recuperação

O caso:

```text
CT24
```

verifica se o usuário consegue corrigir uma informação inválida e posteriormente realizar o cadastro normalmente.

---

# 💻 Próxima Etapa: Automatização com TypeScript e Jest

Depois de documentarmos nossos casos de teste, vamos transformar essas situações em testes automatizados.

Podemos criar uma classe:

```text
UsuarioService
```

com um método:

```text
cadastrarUsuario()
```

A estrutura inicial poderá ser:

```ts
export class UsuarioService {

  cadastrarUsuario(
    id: number,
    nome: string,
    usuario: string,
    senha: string,
    observacao?: string
  ) {

    // As regras de negócio serão implementadas aqui.

  }
}
```

---

# 🧪 Transformando Caso de Teste em Jest

Cada caso documentado poderá virar um teste.

Por exemplo, o `CT03` poderá começar assim:

```ts
it('CT03 deve impedir cadastro com ID duplicado', () => {

  // Arrange
  // Preparar os dados necessários para o teste


  // Act
  // Executar a tentativa de cadastro


  // Assert
  // Verificar se o resultado está correto

});
```

---

# 🧠 Lembrando o Padrão AAA

Durante a implementação dos testes vamos utilizar:

```text
AAA
```

Que significa:

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

---

# 🎯 Desafio

Depois de analisar todos os casos, implemente o cadastro de usuários e crie os testes automatizados utilizando TypeScript e Jest.

Seu projeto deverá verificar principalmente:

* cadastro válido
* campos obrigatórios
* ID duplicado
* usuário duplicado
* espaços em branco
* dados válidos diferentes
* cenários de erro
* recuperação depois de um erro

---

# 🏆 Missão

Sua missão não é apenas provar que o cadastro funciona.

Sua missão é tentar encontrar situações em que ele possa falhar.

> 🐞 Um bug encontrado durante o teste é um problema a menos encontrado pelo usuário.

---

**Prof. Éder Silva**