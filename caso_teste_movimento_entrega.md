# 🚚 Caso de Teste: Movimento de Entrega

## 📚 Objetivo da Atividade

Nesta atividade, nós vamos elaborar os casos de teste para o movimento de entrega de um sistema de delivery.

Nosso objetivo será verificar se uma entrega pode ser criada, iniciada, atualizada e finalizada corretamente.

Também vamos testar situações de erro, dados inválidos e mudanças incorretas de status.

> Nosso objetivo não é testar apenas o caminho que funciona. Precisamos descobrir também o que acontece quando algo dá errado.

---

# 🎯 Funcionalidade

O sistema deverá controlar o movimento de entrega dos pedidos.

Uma entrega possuirá os seguintes campos:

| Campo | Tipo sugerido | Obrigatório |
| :--- | :--- | :---: |
| ID da Entrega | number | Sim |
| ID do Pedido | number | Sim |
| Entregador | string | Sim |
| Endereço | string | Sim |
| Status | string | Sim |
| Horário de Saída | Date | Conforme status |
| Horário de Entrega | Date | Conforme status |
| Observação | string | Não |

---

# 📦 Exemplo de Entrega

```text
ID da Entrega: 1001
ID do Pedido: 500
Entregador: Carlos Silva
Endereço: Rua das Flores, 150
Status: SAIU PARA ENTREGA
Horário de Saída: 19:30
Horário de Entrega:
Observação: Entregar na portaria
```

---

# 🔄 Status da Entrega

Para simplificar nosso exercício, utilizaremos os seguintes status:

```text
AGUARDANDO
SAIU PARA ENTREGA
ENTREGUE
CANCELADA
```

O fluxo normal será:

```text
AGUARDANDO
    ↓
SAIU PARA ENTREGA
    ↓
ENTREGUE
```

Também poderá ocorrer:

```text
AGUARDANDO
    ↓
CANCELADA
```

ou:

```text
SAIU PARA ENTREGA
    ↓
CANCELADA
```

---

# 📋 Regras de Negócio

O movimento de entrega deverá respeitar as seguintes regras:

1. O ID da entrega é obrigatório.
2. Não poderão existir duas entregas com o mesmo ID.
3. O ID do pedido é obrigatório.
4. O pedido informado deverá existir.
5. Um mesmo pedido não poderá possuir duas entregas ativas.
6. O entregador é obrigatório para iniciar uma entrega.
7. O endereço é obrigatório.
8. Uma nova entrega deverá iniciar com status `AGUARDANDO`.
9. Uma entrega somente poderá sair para entrega se estiver `AGUARDANDO`.
10. Ao sair para entrega, o horário de saída deverá ser registrado.
11. Uma entrega somente poderá ser finalizada se estiver `SAIU PARA ENTREGA`.
12. Ao finalizar a entrega, o horário de entrega deverá ser registrado.
13. Uma entrega já entregue não poderá voltar para `AGUARDANDO`.
14. Uma entrega já entregue não poderá ser entregue novamente.
15. Uma entrega cancelada não poderá ser finalizada.
16. Uma entrega cancelada não poderá voltar para um status anterior.
17. A observação será opcional.
18. O horário de entrega não poderá ser anterior ao horário de saída.

---

# 🧪 Casos de Teste

| Caso | Cenário | Resultado esperado |
| :--- | :--- | :--- |
| CT01 | Criar entrega com dados válidos | Entrega criada |
| CT02 | Criar entrega sem observação | Entrega criada |
| CT03 | Criar entrega com ID duplicado | Erro: ID da entrega já cadastrado |
| CT04 | Criar entrega sem ID | Erro: ID obrigatório |
| CT05 | Criar entrega sem pedido | Erro: Pedido obrigatório |
| CT06 | Informar pedido inexistente | Erro: Pedido não encontrado |
| CT07 | Criar segunda entrega ativa para o mesmo pedido | Erro: Pedido já possui entrega |
| CT08 | Criar entrega sem endereço | Erro: Endereço obrigatório |
| CT09 | Endereço contendo apenas espaços | Erro: Endereço obrigatório |
| CT10 | Criar entrega válida | Status inicial AGUARDANDO |
| CT11 | Iniciar entrega válida | Status alterado para SAIU PARA ENTREGA |
| CT12 | Iniciar entrega sem entregador | Erro: Entregador obrigatório |
| CT13 | Entregador contendo somente espaços | Erro: Entregador obrigatório |
| CT14 | Iniciar entrega duas vezes | Operação bloqueada |
| CT15 | Iniciar entrega cancelada | Operação bloqueada |
| CT16 | Iniciar entrega já entregue | Operação bloqueada |
| CT17 | Iniciar entrega | Horário de saída registrado |
| CT18 | Finalizar entrega em andamento | Status alterado para ENTREGUE |
| CT19 | Finalizar entrega aguardando | Operação bloqueada |
| CT20 | Finalizar entrega cancelada | Operação bloqueada |
| CT21 | Finalizar entrega já entregue | Operação bloqueada |
| CT22 | Finalizar entrega válida | Horário de entrega registrado |
| CT23 | Horário de entrega anterior à saída | Operação bloqueada |
| CT24 | Cancelar entrega aguardando | Status alterado para CANCELADA |
| CT25 | Cancelar entrega em andamento | Status alterado para CANCELADA |
| CT26 | Cancelar entrega já entregue | Operação bloqueada |
| CT27 | Cancelar entrega duas vezes | Operação bloqueada |
| CT28 | Alterar entrega cancelada para aguardando | Operação bloqueada |
| CT29 | Alterar entrega entregue para aguardando | Operação bloqueada |
| CT30 | Alterar entrega entregue para em andamento | Operação bloqueada |
| CT31 | Observação vazia | Permitido |
| CT32 | Observação preenchida | Permitido |
| CT33 | Nome do entregador com acentos | Permitido |
| CT34 | Endereço com número e complemento | Permitido |
| CT35 | Buscar entrega existente | Entrega encontrada |
| CT36 | Buscar entrega inexistente | Erro ou resultado não encontrado |
| CT37 | Listar entregas sem registros | Lista vazia |
| CT38 | Listar várias entregas | Todas as entregas retornadas |
| CT39 | Entrega completa seguindo fluxo correto | Processo concluído |
| CT40 | Tentar executar operação depois da finalização | Operação bloqueada |

---

# 🟢 CT01: Criar uma Entrega

## Dados

```text
ID da Entrega: 1001
ID do Pedido: 500
Endereço: Rua das Flores, 150
Observação: Entregar na portaria
```

## Resultado esperado

```text
Entrega criada com sucesso.
Status: AGUARDANDO
```

O sistema não deverá permitir que o usuário escolha inicialmente:

```text
ENTREGUE
```

A nova entrega deverá começar como:

```text
AGUARDANDO
```

---

# 🔴 CT03: ID de Entrega Duplicado

Já existe:

```text
ID da Entrega: 1001
Pedido: 500
```

Tentamos cadastrar:

```text
ID da Entrega: 1001
Pedido: 501
```

Mesmo sendo outro pedido, o ID da entrega está duplicado.

## Resultado esperado

```text
Entrega não cadastrada.
ID da entrega já cadastrado.
```

---

# 🔴 CT06: Pedido Inexistente

Tentativa:

```text
ID da Entrega: 1002
ID do Pedido: 9999
Endereço: Rua Central, 200
```

Se o pedido `9999` não existir, a entrega não deverá ser criada.

## Resultado esperado

```text
Pedido não encontrado.
```

---

# 🔴 CT07: Duas Entregas para o Mesmo Pedido

Imagine que o pedido:

```text
500
```

já possui:

```text
Entrega: 1001
Status: SAIU PARA ENTREGA
```

Tentamos criar:

```text
Entrega: 1002
Pedido: 500
```

## Resultado esperado

```text
Pedido já possui uma entrega ativa.
```

---

# 🛵 CT11: Iniciar uma Entrega

Temos:

```text
ID: 1001
Status: AGUARDANDO
Entregador: Carlos Silva
```

Executamos:

```text
Iniciar entrega
```

## Resultado esperado

```text
Status: SAIU PARA ENTREGA
```

O sistema também deverá registrar:

```text
Horário de Saída
```

---

# ⏰ CT17: Registrar Horário de Saída

Antes:

```text
Status: AGUARDANDO
Horário de Saída: vazio
```

Depois de iniciar:

```text
Status: SAIU PARA ENTREGA
Horário de Saída: 19:30
```

O horário deverá ser registrado automaticamente pelo sistema ou informado conforme a regra definida para o projeto.

---

# 📦 CT18: Finalizar uma Entrega

Temos:

```text
ID: 1001
Status: SAIU PARA ENTREGA
Horário de Saída: 19:30
```

Executamos:

```text
Finalizar entrega
```

## Resultado esperado

```text
Status: ENTREGUE
Horário de Entrega: 20:05
```

---

# 🔴 CT19: Finalizar sem Iniciar

Temos:

```text
Status: AGUARDANDO
```

Tentamos:

```text
Finalizar entrega
```

## Resultado esperado

```text
Operação não permitida.
A entrega ainda não saiu para entrega.
```

Esse teste é importante porque o sistema não deverá permitir:

```text
AGUARDANDO
    ↓
ENTREGUE
```

O fluxo correto é:

```text
AGUARDANDO
    ↓
SAIU PARA ENTREGA
    ↓
ENTREGUE
```

---

# ⏰ CT23: Horário de Entrega Inválido

Considere:

```text
Horário de Saída: 20:00
Horário de Entrega: 19:30
```

Isso significaria que o pedido foi entregue antes de sair.

## Resultado esperado

```text
Operação não permitida.
Horário de entrega inválido.
```

---

# ❌ CT24: Cancelar Entrega

Temos:

```text
Status: AGUARDANDO
```

Executamos:

```text
Cancelar entrega
```

## Resultado esperado

```text
Status: CANCELADA
```

---

# 🔴 CT26: Cancelar uma Entrega já Realizada

Temos:

```text
Status: ENTREGUE
```

Tentamos:

```text
Cancelar entrega
```

## Resultado esperado

```text
Operação não permitida.
A entrega já foi finalizada.
```

---

# 🔴 CT28: Reativar Entrega Cancelada

Temos:

```text
Status: CANCELADA
```

Tentamos alterar para:

```text
AGUARDANDO
```

## Resultado esperado

```text
Operação não permitida.
Entrega cancelada.
```

---

# 🔄 Teste Completo do Fluxo

Um dos testes mais importantes será verificar todo o ciclo da entrega.

## Passo 1

Criamos:

```text
ID da Entrega: 1001
Pedido: 500
Endereço: Rua das Flores, 150
```

Esperado:

```text
Status: AGUARDANDO
```

## Passo 2

Definimos:

```text
Entregador: Carlos Silva
```

E iniciamos a entrega.

Esperado:

```text
Status: SAIU PARA ENTREGA
Horário de Saída: registrado
```

## Passo 3

Finalizamos.

Esperado:

```text
Status: ENTREGUE
Horário de Entrega: registrado
```

Fluxo completo:

```text
PEDIDO
  ↓
ENTREGA CRIADA
  ↓
AGUARDANDO
  ↓
SAIU PARA ENTREGA
  ↓
ENTREGUE
```

---

# 📊 Matriz de Transição de Status

Uma forma interessante de testar o movimento é verificar quais mudanças de status são permitidas.

| Status atual | Novo status | Permitido |
| :--- | :--- | :---: |
| AGUARDANDO | SAIU PARA ENTREGA | ✅ |
| AGUARDANDO | CANCELADA | ✅ |
| AGUARDANDO | ENTREGUE | ❌ |
| SAIU PARA ENTREGA | ENTREGUE | ✅ |
| SAIU PARA ENTREGA | CANCELADA | ✅ |
| SAIU PARA ENTREGA | AGUARDANDO | ❌ |
| ENTREGUE | AGUARDANDO | ❌ |
| ENTREGUE | SAIU PARA ENTREGA | ❌ |
| ENTREGUE | CANCELADA | ❌ |
| CANCELADA | AGUARDANDO | ❌ |
| CANCELADA | SAIU PARA ENTREGA | ❌ |
| CANCELADA | ENTREGUE | ❌ |

---

# 🧠 Por que Testar os Status?

Quando trabalhamos com movimentações, não basta testar os campos.

Precisamos testar também o estado do objeto.

Por exemplo:

Uma entrega pode possuir todos os dados corretos e mesmo assim uma operação ser inválida.

Considere:

```text
ID: 1001
Pedido: 500
Entregador: Carlos
Endereço: Rua Central, 100
Status: ENTREGUE
```

Os dados estão corretos.

Mas executar:

```text
Iniciar entrega
```

deve ser proibido porque ela já foi entregue.

Isso é uma regra de negócio.

---

# 🧪 Categorias dos Casos de Teste

## ✅ Testes Positivos

Verificam operações que deverão funcionar.

```text
CT01
CT02
CT10
CT11
CT17
CT18
CT22
CT24
CT25
CT31
CT32
CT33
CT34
CT35
CT37
CT38
CT39
```

---

## ❌ Validações

Verificam campos obrigatórios e dados incorretos.

```text
CT03
CT04
CT05
CT06
CT07
CT08
CT09
CT12
CT13
CT23
```

---

## 🔄 Transições de Status

Verificam se a entrega segue o fluxo correto.

```text
CT14
CT15
CT16
CT18
CT19
CT20
CT21
CT24
CT25
CT26
CT27
CT28
CT29
CT30
CT40
```

---

# 💻 Próxima Etapa: Automatização com TypeScript e Jest

Depois de documentarmos os casos, podemos criar:

```text
EntregaService
```

Uma estrutura inicial poderia ser:

```ts
export class EntregaService {

  criarEntrega() {

  }

  iniciarEntrega() {

  }

  finalizarEntrega() {

  }

  cancelarEntrega() {

  }

  buscarPorId() {

  }

  listarEntregas() {

  }

}
```

---

# 🧪 Transformando os Casos em Jest

Por exemplo:

```ts
it('CT11 deve iniciar uma entrega que está aguardando', () => {

  // Arrange
  // Preparar uma entrega com status AGUARDANDO


  // Act
  // Iniciar a entrega


  // Assert
  // Verificar se mudou para SAIU PARA ENTREGA

});
```

Outro exemplo:

```ts
it('CT19 não deve finalizar uma entrega que ainda está aguardando', () => {

  // Arrange


  // Act + Assert
  expect(() => {
    // tentar finalizar
  }).toThrow();

});
```

---

# 🧠 Padrão AAA

Continuaremos utilizando:

```text
Arrange
Act
Assert
```

Ou:

```text
Preparar
Executar
Validar
```

---

# 🎯 Desafio dos Alunos

Implemente o movimento de entrega utilizando TypeScript e depois automatize os principais casos utilizando Jest.

Seu sistema deverá permitir:

```text
Criar entrega
Iniciar entrega
Finalizar entrega
Cancelar entrega
Buscar entrega
Listar entregas
```

Também deverá impedir operações que violem as regras de negócio.

---

# ⭐ Desafio Extra

Depois de concluir os testes principais, implemente uma regra adicional:

Uma entrega não poderá permanecer com status:

```text
SAIU PARA ENTREGA
```

por mais de:

```text
2 horas
```

Crie um método que identifique entregas atrasadas e escreva testes para:

```text
Entrega dentro do prazo
Entrega exatamente no limite
Entrega acima de 2 horas
Entrega já finalizada
Entrega cancelada
```

---

# 🏆 Missão

O objetivo desta atividade não é apenas verificar se conseguimos entregar um pedido.

Precisamos garantir que o pedido percorra um fluxo válido do início ao fim.

> 🚚 Em um sistema de entregas, não basta saber onde o pedido está. Precisamos garantir que ele chegou até ali seguindo as regras corretas.

---

**Prof. Éder Silva**
