
# Aula: Requisitos de Testes de Sistemas

## 1. Objetivo da aula

Nesta aula nós vamos entender o que são requisitos de sistemas e qual é a relação deles com os testes de software.

Nós também vamos estudar dois tipos muito importantes de requisitos:

1. Requisitos Funcionais
2. Requisitos Não Funcionais

Ao final da aula, nós deveremos conseguir:

1. Entender o que é um requisito
2. Identificar requisitos funcionais
3. Identificar requisitos não funcionais
4. Relacionar requisitos com testes
5. Criar exemplos simples de testes
6. Entender por que testar requisitos é tão importante

---

# 2. Antes de falar em testes, precisamos falar em requisitos

Quando uma empresa decide desenvolver um sistema, normalmente existe algum problema que precisa ser resolvido.

Vamos imaginar uma situação simples.

Uma pizzaria quer criar um sistema de delivery.

O proprietário da pizzaria diz:

O sistema precisa permitir cadastrar clientes.

O sistema precisa permitir cadastrar produtos.

O cliente precisa conseguir fazer um pedido.

O sistema precisa calcular o valor total da compra.

O atendente precisa conseguir acompanhar os pedidos.

Todas essas necessidades podem virar requisitos do sistema.

Podemos entender requisito como uma necessidade, uma função, uma característica ou uma regra que o sistema deverá atender.

De forma simples:

## Requisito é algo que o sistema precisa fazer ou precisa possuir.

---

# 3. De onde surgem os requisitos?

Os requisitos normalmente surgem através de conversas com pessoas que conhecem o negócio.

Essas pessoas podem ser:

Clientes

Usuários

Gestores

Funcionários

Analistas

Desenvolvedores

Especialistas da área

Imagine que nós vamos desenvolver um sistema para uma escola.

Antes de começar a programar, precisamos conversar com a escola.

Podemos perguntar:

Quem utilizará o sistema?

Quais informações precisam ser cadastradas?

Quem pode cadastrar alunos?

Quem pode alterar notas?

Quem pode visualizar informações financeiras?

O sistema precisa funcionar pelo celular?

Quantos usuários utilizarão o sistema ao mesmo tempo?

Todas essas respostas ajudam a formar os requisitos.

---

# 4. Por que precisamos definir requisitos?

Imagine que um cliente peça:

Quero um sistema para controlar minha loja.

Essa informação ainda é muito vaga.

Precisamos descobrir exatamente o que esse sistema precisa fazer.

Podemos então perguntar:

O sistema terá cadastro de clientes?

Terá cadastro de produtos?

Controlará estoque?

Fará vendas?

Emitirá relatórios?

Terá usuários diferentes?

Precisará de senha?

Funcionará pela internet?

Quanto mais entendermos os requisitos, menor será a chance de desenvolver algo diferente do que o cliente realmente precisa.

---

# 5. Requisitos Funcionais

Agora vamos conhecer nosso primeiro tipo de requisito.

## Requisitos Funcionais

Os requisitos funcionais descrevem aquilo que o sistema deverá fazer.

Eles representam funções, operações e comportamentos do sistema.

Podemos fazer uma pergunta simples:

## O que o sistema deve fazer?

A resposta normalmente estará relacionada a um requisito funcional.

---

# 6. Exemplos de Requisitos Funcionais

Vamos imaginar um sistema de biblioteca.

Poderíamos ter os seguintes requisitos:

RF01. O sistema deve permitir cadastrar livros.

RF02. O sistema deve permitir cadastrar leitores.

RF03. O sistema deve permitir realizar empréstimos.

RF04. O sistema deve permitir registrar devoluções.

RF05. O sistema deve permitir consultar livros disponíveis.

RF06. O sistema deve calcular multas por atraso.

RF07. O sistema deve permitir localizar livros pelo título.

Percebam que todos esses requisitos representam ações realizadas pelo sistema.

---

# 7. Outro exemplo: sistema de delivery

Vamos construir juntos um sistema simples de delivery.

Primeiro pensamos nas funções principais.

Nós queremos que o sistema permita:

Cadastrar clientes

Cadastrar produtos

Fazer pedidos

Adicionar produtos ao pedido

Calcular o valor total

Escolher a forma de pagamento

Cancelar pedidos

Consultar pedidos

Agora podemos transformar essas necessidades em requisitos.

RF01. O sistema deve permitir cadastrar clientes.

RF02. O sistema deve permitir cadastrar produtos.

RF03. O sistema deve permitir criar pedidos.

RF04. O sistema deve permitir adicionar produtos ao pedido.

RF05. O sistema deve calcular automaticamente o valor total do pedido.

RF06. O sistema deve permitir escolher uma forma de pagamento.

RF07. O sistema deve permitir cancelar pedidos.

RF08. O sistema deve permitir consultar pedidos anteriores.

---

# 8. Como podemos testar um requisito funcional?

Vamos pegar este requisito:

RF01. O sistema deve permitir cadastrar clientes.

Agora precisamos pensar:

Como nós podemos verificar se esse requisito realmente funciona?

Podemos criar alguns testes.

### Teste 1

Cadastrar um cliente preenchendo todos os campos corretamente.

Resultado esperado:

O sistema deverá salvar o cliente.

### Teste 2

Tentar cadastrar um cliente sem informar o nome.

Resultado esperado:

O sistema deverá impedir o cadastro e apresentar uma mensagem.

### Teste 3

Cadastrar dois clientes diferentes.

Resultado esperado:

Os dois clientes deverão aparecer na lista de clientes.

Percebam que nós começamos com um requisito e transformamos esse requisito em testes.

---

# 9. Requisitos Não Funcionais

Agora vamos estudar o segundo tipo.

Os requisitos não funcionais não descrevem necessariamente uma função do sistema.

Eles descrevem características, condições, limitações, desempenho, segurança, disponibilidade e qualidade.

Podemos fazer outra pergunta:

## Como o sistema deverá funcionar?

A resposta normalmente estará relacionada a um requisito não funcional.

---

# 10. Exemplos de Requisitos Não Funcionais

Vamos continuar com nosso sistema de delivery.

Podemos ter os seguintes requisitos:

RNF01. O sistema deverá carregar a tela principal em até 3 segundos.

RNF02. O sistema deverá exigir senha para acessar a área administrativa.

RNF03. A senha deverá possuir pelo menos 8 caracteres.

RNF04. O sistema deverá funcionar nos navegadores Chrome, Edge e Firefox.

RNF05. O sistema deverá realizar cópia de segurança diariamente.

RNF06. O sistema deverá suportar 200 usuários conectados simultaneamente.

RNF07. O sistema deverá proteger os dados dos clientes.

Percebam que esses requisitos não criam exatamente uma nova função.

Eles definem características ou condições relacionadas ao funcionamento do sistema.

---

# 11. Comparando Requisito Funcional e Não Funcional

Vamos observar alguns exemplos.

## Exemplo 1

O sistema deve permitir cadastrar clientes.

Tipo:

Requisito Funcional.

Por quê?

Porque estamos dizendo o que o sistema deverá fazer.

## Exemplo 2

O cadastro do cliente deverá ser concluído em até 2 segundos.

Tipo:

Requisito Não Funcional.

Por quê?

Porque estamos definindo uma característica de desempenho.

---

# 12. Outro exemplo

O sistema deve permitir realizar login.

Requisito Funcional.

Agora veja:

A senha deverá possuir pelo menos 8 caracteres.

Requisito Não Funcional.

O login deve ser realizado em até 3 segundos.

Requisito Não Funcional.

Após 5 tentativas incorretas de senha, o usuário deverá ser bloqueado.

Pode ser tratado como requisito funcional ou requisito relacionado à segurança, dependendo da documentação adotada pelo projeto.

O importante é compreender o comportamento esperado.

---

# 13. O que são requisitos de teste?

Agora chegamos diretamente ao nosso assunto principal.

Quando temos os requisitos do sistema, precisamos verificar se eles realmente foram implementados corretamente.

Então criamos testes baseados nesses requisitos.

Podemos dizer que:

## Os requisitos de teste definem o que precisa ser verificado no sistema.

Nós analisamos cada requisito e criamos situações para verificar se o sistema atende ao comportamento esperado.

---

# 14. Exemplo completo

Vamos imaginar o seguinte requisito:

RF01. O sistema deve permitir cadastrar usuários.

O cadastro possui os campos:

ID

Nome

Usuário

Senha

Observação

Também temos algumas regras.

O ID não pode se repetir.

O usuário não pode se repetir.

O nome não pode ficar vazio.

A senha não pode ficar vazia.

Agora começamos a pensar como testadores.

Precisamos testar somente o cenário correto?

Não.

Precisamos testar também situações incorretas.

---

# 15. Criando alguns testes

## Teste 1

Cadastrar usuário com todos os campos corretos.

Entrada:

ID: 1

Nome: Maria

Usuário: maria

Senha: 123456

Observação: Cliente novo

Resultado esperado:

Usuário cadastrado com sucesso.

---

## Teste 2

Cadastrar outro usuário utilizando o mesmo ID.

Entrada:

ID: 1

Nome: Carlos

Usuário: carlos

Senha: 654321

Resultado esperado:

O sistema deverá impedir o cadastro.

Mensagem esperada:

ID já cadastrado.

---

## Teste 3

Cadastrar usuário repetido.

Entrada:

ID: 2

Nome: João

Usuário: maria

Senha: 987654

Resultado esperado:

O sistema deverá impedir o cadastro.

Mensagem esperada:

Usuário já cadastrado.

---

## Teste 4

Cadastrar sem nome.

Entrada:

ID: 3

Nome vazio

Usuário: joao

Senha: 123456

Resultado esperado:

O sistema deverá impedir o cadastro.

Mensagem esperada:

Nome obrigatório.

---

## Teste 5

Cadastrar sem senha.

Entrada:

ID: 4

Nome: Ana

Usuário: ana

Senha vazia

Resultado esperado:

O sistema deverá impedir o cadastro.

Mensagem esperada:

Senha obrigatória.

---

# 16. Por que precisamos testar requisitos?

Essa é uma pergunta muito importante.

Podemos pensar:

Se o programador terminou o sistema e ele abriu corretamente, então está tudo funcionando?

Não necessariamente.

Um sistema pode abrir normalmente e ainda possuir diversos problemas.

Por exemplo:

Pode permitir clientes duplicados.

Pode calcular valores errados.

Pode aceitar senhas inválidas.

Pode excluir informações incorretamente.

Pode apresentar erros ao receber determinados dados.

Pode ficar lento quando muitos usuários estiverem conectados.

Pode apresentar problemas de segurança.

Por isso nós realizamos testes.

---

# 17. Os testes ajudam a verificar se o sistema atende ao que foi solicitado

Se o requisito diz:

O sistema deve permitir alterar clientes.

Precisamos testar a alteração.

Se o requisito diz:

O sistema deve impedir IDs repetidos.

Precisamos tentar cadastrar IDs repetidos.

Se o requisito diz:

O sistema deve carregar a tela em até 3 segundos.

Precisamos medir o tempo de carregamento.

Cada requisito pode gerar um ou vários testes.

---

# 18. Devemos testar somente situações corretas?

Não.

Essa é uma das partes mais importantes dos testes.

Nós devemos testar situações corretas e incorretas.

Vamos imaginar um campo chamado idade.

O sistema aceita pessoas entre 18 e 100 anos.

Nós podemos testar:

18

50

100

Mas também precisamos testar:

17

101

0

Número negativo

Campo vazio

Letras

Símbolos

Quanto mais situações relevantes testarmos, maior será nossa possibilidade de encontrar problemas.

---

# 19. Testando limites

Muitos problemas aparecem nos valores próximos aos limites permitidos.

Vamos imaginar:

A senha precisa possuir no mínimo 8 caracteres.

Nós poderíamos testar:

7 caracteres

8 caracteres

9 caracteres

O teste mais importante provavelmente será o de 7 e 8 caracteres.

Por quê?

Porque estamos testando exatamente a mudança entre o valor inválido e o valor válido.

---

# 20. Exemplo de limite em idade

Imagine a seguinte regra:

Somente maiores de 18 anos podem realizar o cadastro.

Podemos testar:

17 anos

18 anos

19 anos

Assim conseguimos verificar exatamente o comportamento próximo ao limite.

---

# 21. Testando campos obrigatórios

Vamos imaginar um cadastro de cliente.

Campos:

Nome

CPF

Telefone

Email

Se todos forem obrigatórios, precisamos testar cada um deles.

Podemos tentar:

Cadastrar sem nome

Cadastrar sem CPF

Cadastrar sem telefone

Cadastrar sem email

Não basta testar todos vazios ao mesmo tempo.

Precisamos identificar qual campo está causando o comportamento.

---

# 22. Testes positivos

Chamamos de teste positivo aquele em que usamos informações válidas esperando que o sistema funcione normalmente.

Exemplo:

Cadastrar um cliente com todos os dados corretos.

Resultado esperado:

Cliente cadastrado com sucesso.

---

# 23. Testes negativos

Chamamos de teste negativo aquele em que utilizamos informações inválidas ou situações não permitidas.

Exemplo:

Cadastrar cliente sem nome.

Resultado esperado:

Sistema impede o cadastro.

Outro exemplo:

Cadastrar um usuário já existente.

Resultado esperado:

Sistema impede o cadastro duplicado.

Esses testes são extremamente importantes.

---

# 24. Exemplo com login

Vamos imaginar um sistema de login.

Requisito:

O sistema deve permitir acesso utilizando usuário e senha válidos.

Agora vamos criar alguns testes.

### Cenário 1

Usuário correto.

Senha correta.

Resultado:

Login realizado.

### Cenário 2

Usuário correto.

Senha errada.

Resultado:

Acesso negado.

### Cenário 3

Usuário inexistente.

Resultado:

Acesso negado.

### Cenário 4

Usuário vazio.

Resultado:

Sistema solicita usuário.

### Cenário 5

Senha vazia.

Resultado:

Sistema solicita senha.

Percebam que apenas um requisito gerou vários testes.

---

# 25. Exemplo com sistema de vendas

Vamos imaginar o requisito:

RF10. O sistema deverá permitir adicionar produtos a uma venda.

Nós podemos testar:

Adicionar um produto existente.

Adicionar vários produtos.

Adicionar o mesmo produto duas vezes.

Tentar adicionar produto inexistente.

Tentar adicionar produto sem estoque.

Adicionar quantidade 1.

Adicionar quantidade 10.

Tentar adicionar quantidade 0.

Tentar adicionar quantidade negativa.

Cada uma dessas situações pode revelar um comportamento diferente.

---

# 26. Requisito funcional relacionado a estoque

Requisito:

RF11. Após finalizar uma venda, o estoque do produto deverá ser reduzido.

Vamos testar.

Estoque inicial:

10 unidades.

Venda:

2 unidades.

Resultado esperado:

Estoque final:

8 unidades.

Agora podemos fazer outro teste.

Estoque inicial:

1 unidade.

Venda:

1 unidade.

Resultado esperado:

Estoque final:

0 unidades.

Agora outro teste.

Estoque inicial:

0 unidades.

Tentativa de venda:

1 unidade.

Resultado esperado:

O sistema deverá impedir a venda.

---

# 27. Requisitos não funcionais de desempenho

Agora vamos imaginar:

RNF01. A tela de produtos deverá ser carregada em até 3 segundos.

Como podemos testar?

Abrimos a tela e medimos o tempo.

Se carregar em:

1 segundo

Requisito atendido.

Se carregar em:

2 segundos

Requisito atendido.

Se carregar em:

6 segundos

Requisito não atendido.

---

# 28. Requisitos não funcionais de segurança

Imagine:

RNF02. Após 5 tentativas incorretas de senha, o usuário deverá ser bloqueado.

Podemos testar:

Primeira tentativa incorreta.

Segunda tentativa incorreta.

Terceira tentativa incorreta.

Quarta tentativa incorreta.

Quinta tentativa incorreta.

Resultado esperado:

Usuário bloqueado.

Depois podemos tentar fazer login novamente.

Resultado esperado:

Acesso bloqueado.

---

# 29. Requisitos de compatibilidade

Outro tipo de requisito não funcional pode definir onde o sistema deverá funcionar.

Exemplo:

O sistema deverá funcionar corretamente nos navegadores:

Google Chrome

Microsoft Edge

Mozilla Firefox

Nós então precisamos testar o sistema nesses navegadores.

Pode acontecer de funcionar corretamente no Chrome e apresentar problemas no Firefox.

---

# 30. Requisitos de usabilidade

Também podemos ter requisitos relacionados à facilidade de utilização.

Exemplo:

O usuário deverá conseguir finalizar uma compra utilizando no máximo 5 telas.

Outro exemplo:

As mensagens de erro deverão explicar claramente o problema encontrado.

Por exemplo, esta mensagem não ajuda muito:

Erro 9274.

Uma mensagem melhor seria:

Informe o nome do cliente.

Essa mensagem orienta o usuário.

---

# 31. Requisitos precisam ser claros

Um requisito ruim seria:

O sistema deve ser rápido.

Pergunta:

O que significa rápido?

1 segundo?

5 segundos?

30 segundos?

Esse requisito é difícil de testar.

Uma versão melhor seria:

A tela de clientes deverá ser carregada em até 3 segundos.

Agora temos algo que podemos medir.

---

# 32. Outro exemplo de requisito ruim

Requisito:

O sistema deverá ter uma senha segura.

Pergunta:

O que significa senha segura?

Precisamos especificar.

Uma versão melhor seria:

A senha deverá possuir no mínimo 8 caracteres e deverá conter pelo menos uma letra e um número.

Agora conseguimos criar testes.

---

# 33. A relação entre requisito e teste

Nós podemos pensar da seguinte maneira:

Cliente possui uma necessidade.

Essa necessidade vira um requisito.

O requisito é implementado pelo desenvolvedor.

Depois o requisito é testado.

Se funcionar corretamente, o teste passa.

Se não funcionar corretamente, o teste falha.

Quando encontramos um problema, registramos um defeito.

O desenvolvedor corrige.

Depois realizamos o teste novamente.

Esse processo faz parte do desenvolvimento profissional de software.

---

# 34. Exemplo de ciclo

Vamos imaginar:

Requisito:

O sistema deve impedir dois usuários com o mesmo nome de usuário.

Teste:

Cadastrar usuário joao.

Resultado:

Cadastro realizado.

Depois tentamos cadastrar outro usuário joao.

Resultado esperado:

Cadastro bloqueado.

Mas durante o teste acontece isto:

O sistema permite o cadastro.

Então encontramos um defeito.

O programador corrige o sistema.

Depois repetimos o teste.

Agora o sistema bloqueia corretamente.

O teste passa.

---

# 35. Testar não significa tentar destruir o sistema

Às vezes pensamos que o testador está tentando atrapalhar o desenvolvedor.

Na verdade, estamos trabalhando juntos.

Nosso objetivo é encontrar problemas antes que o usuário encontre.

É muito melhor encontrarmos um erro durante o desenvolvimento do que o cliente encontrar o erro usando o sistema.

---

# 36. Quanto antes encontrarmos um problema, melhor

Imagine que um erro seja encontrado durante o desenvolvimento.

O programador pode corrigir rapidamente.

Agora imagine o mesmo erro sendo encontrado depois que o sistema já possui:

Milhares de clientes cadastrados

Milhares de vendas

Dados financeiros

Funcionários utilizando o sistema

Corrigir o problema poderá ser muito mais difícil.

Por isso os testes devem acontecer durante o desenvolvimento.

---

# 37. Exercício guiado

Agora nós vamos criar alguns requisitos para um sistema de biblioteca.

Nosso sistema deverá possuir:

Cadastro de livros

Cadastro de leitores

Empréstimo de livros

Devolução de livros

Consulta de livros

Agora vamos transformar isso em requisitos.

RF01. O sistema deve permitir cadastrar livros.

RF02. O sistema deve permitir cadastrar leitores.

RF03. O sistema deve permitir realizar empréstimos.

RF04. O sistema deve permitir registrar devoluções.

RF05. O sistema deve permitir consultar livros.

Agora adicionamos algumas regras.

Um livro não poderá ser emprestado se já estiver emprestado.

O leitor poderá possuir no máximo 3 livros emprestados.

O empréstimo deverá possuir data de retirada.

O empréstimo deverá possuir data prevista para devolução.

---

# 38. Criando os testes juntos

Agora vamos testar:

RF03. O sistema deve permitir realizar empréstimos.

Teste 1:

Leitor válido e livro disponível.

Resultado esperado:

Empréstimo realizado.

Teste 2:

Livro já emprestado.

Resultado esperado:

Empréstimo bloqueado.

Teste 3:

Leitor já possui 3 livros.

Resultado esperado:

Novo empréstimo bloqueado.

Teste 4:

Livro inexistente.

Resultado esperado:

Sistema informa que o livro não existe.

Teste 5:

Leitor inexistente.

Resultado esperado:

Sistema informa que o leitor não existe.

---

# 39. Exercício para os alunos

Agora nós vamos imaginar que estamos desenvolvendo um sistema para uma academia.

O sistema deverá possuir:

Cadastro de alunos

Cadastro de professores

Cadastro de planos

Controle de mensalidades

Controle de acesso

Agendamento de avaliações

Os alunos deverão criar:

5 requisitos funcionais.

5 requisitos não funcionais.

Para cada requisito funcional, criar pelo menos 3 casos de teste.

---

# 40. Exemplo inicial

RF01. O sistema deve permitir cadastrar alunos.

Possíveis testes:

Cadastrar aluno corretamente.

Cadastrar aluno sem nome.

Cadastrar aluno com CPF repetido.

RNF01. A tela de cadastro deverá ser carregada em até 2 segundos.

Possível teste:

Medir o tempo necessário para abrir a tela.

---

# 41. Desafio em grupo

Vamos dividir a turma em grupos.

Cada grupo deverá escolher um sistema.

Sugestões:

Sistema de restaurante

Sistema de escola

Sistema de supermercado

Sistema de hospital

Sistema de estacionamento

Sistema de hotel

Sistema de delivery

Sistema de biblioteca

Depois o grupo deverá definir:

5 requisitos funcionais.

5 requisitos não funcionais.

10 casos de teste.

Depois cada grupo poderá apresentar seu sistema para a turma.

---

# 42. Perguntas para revisão

1. O que é um requisito de sistema?

2. Qual é a diferença entre requisito funcional e não funcional?

3. O que caracteriza um requisito funcional?

4. O que caracteriza um requisito não funcional?

5. Por que devemos testar os requisitos?

6. Um requisito pode gerar vários testes?

7. O que é um teste positivo?

8. O que é um teste negativo?

9. Por que devemos testar valores limites?

10. Por que requisitos precisam ser claros?

---

# 43. Resumo da aula

Hoje nós aprendemos que antes de testar um sistema precisamos entender o que ele deveria fazer.

Essas necessidades são representadas pelos requisitos.

Os requisitos funcionais dizem o que o sistema deve fazer.

Exemplo:

Cadastrar clientes.

Realizar vendas.

Emitir relatórios.

Realizar login.

Os requisitos não funcionais dizem como o sistema deve funcionar ou quais características precisa possuir.

Exemplo:

Tempo de resposta.

Segurança.

Compatibilidade.

Desempenho.

Facilidade de uso.

Disponibilidade.

Depois transformamos esses requisitos em casos de teste.

Nós testamos situações corretas e incorretas.

Também testamos limites, campos obrigatórios, regras de negócio, segurança e desempenho.

Nosso objetivo não é apenas verificar se o sistema abre.

Nosso objetivo é verificar se ele realmente faz aquilo que deveria fazer.

---
