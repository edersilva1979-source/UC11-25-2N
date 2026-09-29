# Projeto: Sistema de Cadastro e Gestão de Eventos

## Contexto

Uma empresa precisa de um **sistema simples de gestão de eventos** onde administradores possam cadastrar eventos e usuários possam se inscrever neles.

O sistema deve permitir o gerenciamento de:

* usuários
* eventos
* inscrições em eventos

Antes de iniciar o desenvolvimento do sistema, a equipe de QA deve **definir todos os casos de teste necessários para validar o sistema**, considerando tanto cenários de **sucesso quanto de erro**.

---

# Objetivo da Atividade

1. Analisar os **requisitos do sistema**
2. Criar **casos de teste para cada requisito**
3. Considerar cenários de:

   * funcionamento correto
   * entradas inválidas
   * erros de sistema
   * limites de dados

> [!IMPORTANT]
> Não será necessário implementar o sistema neste momento.

---

# Requisitos Funcionais

### RF01 — Cadastro de Usuário

O sistema deve permitir cadastrar um novo usuário com as seguintes informações:

* Nome
* Email
* Senha
* Data de nascimento

O email deve ser único no sistema.

---

### RF02 — Login de Usuário

O sistema deve permitir que um usuário faça login utilizando:

* Email
* Senha

Caso as credenciais estejam incorretas, o acesso deve ser negado.

---

### RF03 — Cadastro de Evento

Administradores devem poder cadastrar eventos contendo:

* Nome do evento
* Descrição
* Data do evento
* Número máximo de participantes

---

### RF04 — Listagem de Eventos

O sistema deve permitir visualizar todos os eventos cadastrados.

Cada evento deve exibir:

* Nome
* Data
* Número de vagas disponíveis

---

### RF05 — Inscrição em Evento

Usuários autenticados podem se inscrever em eventos.

Regras:

* Um usuário não pode se inscrever duas vezes no mesmo evento
* Não é possível se inscrever em eventos lotados
* Não é possível se inscrever em eventos que já aconteceram

---

### RF06 — Cancelamento de Inscrição

Um usuário deve poder cancelar sua inscrição em um evento.

Após cancelar:

* a vaga deve ser liberada novamente

---

# Requisitos Não Funcionais

### RNF01 — Validação de Campos

Todos os campos obrigatórios devem ser validados antes de salvar dados no sistema.

---

### RNF02 — Segurança de Senha

A senha deve possuir no mínimo:

* 8 caracteres
* 1 letra maiúscula
* 1 número

---

### RNF03 — Tempo de Resposta

As operações de listagem de eventos devem responder em **até 2 segundos**.

---

### RNF04 — Compatibilidade

O sistema deve funcionar corretamente em:

* Chrome
* Firefox
* Edge

---

### RNF05 — Integridade de Dados

O sistema não deve permitir duplicidade de usuários com o mesmo email.

---

# Tarefa a ser executada

Para **cada requisito**, criar **casos de teste contendo**:

* ID do caso de teste
* Requisito associado
* Descrição do teste
* Dados de entrada
* Resultado esperado

* Tipo de teste (positivo ou negativo)

---

# Exemplo de Caso de Teste

| ID   | Requisito | Descrição                             | Entrada                          | Resultado Esperado             |
|:----:|:---------:|:-------------------------------------:|:--------------------------------:|:------------------------------:|
| CT01 | RF01      | Cadastrar usuário com dados válidos   | Nome, email válido, senha válida | Usuário cadastrado com sucesso |
| CT02 | RF01      | Cadastrar usuário com email duplicado | Email já existente               | Sistema deve impedir cadastro  |
| CT03 | RF02      | Login com senha incorreta             | Email válido + senha errada      | Sistema deve negar acesso      |

---

# Entregáveis

Entregar:

1. Documento contendo **todos os casos de teste**
2. Cada requisito deve possuir **múltiplos testes**, incluindo:

   * casos válidos
   * casos inválidos
   * testes de limite

3. Organização clara e rastreável entre **requisitos e testes**

# Enviar arquivo para o email: eder.silva1979@gmail.com
