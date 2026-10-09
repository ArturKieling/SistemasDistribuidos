# Aula 1 (27/07/2026) — Orientações do Professor e Introdução à Disciplina

## Orientações iniciais do Professor

* Todos os programas deverão ser desenvolvidos utilizando o paradigma de **Programação Orientada a Objetos (POO)**.
* Os projetos deverão seguir os princípios da arquitetura **MVC**, organizando o código em componentes como Model, Controller, Service, Interface e outros que forem necessários.
* Todos os códigos deverão possuir **documentação**, pois os trabalhos sem documentação não serão validados.
* A avaliação será realizada por meio de trabalhos práticos e apresentações no quadro, sem provas tradicionais.

## Introdução à Arquitetura de Sistemas

A arquitetura de sistemas define como os computadores são organizados e como ocorre a comunicação entre eles.

### 1. Modelo Cliente-Servidor

Nesse modelo, um computador solicita informações ou serviços, enquanto outro, responsável por atender às solicitações, envia as respostas.

O modelo de referência **OSI** possui sete camadas:

1. Aplicação;
2. Apresentação;
3. Sessão;
4. Transporte;
5. Rede;
6. Enlace;
7. Física.

O modelo OSI é utilizado principalmente como referência teórica, enquanto o modelo **TCP/IP** é amplamente utilizado na prática para a comunicação em redes.

### 2. Modelo Ponto a Ponto (P2P)

Nesse formato, os computadores podem se comunicar diretamente, sem depender obrigatoriamente de um servidor central. A comunicação ocorre por meio de uma rede e utiliza protocolos como os relacionados ao modelo TCP/IP.

### Características importantes da arquitetura de sistemas

* **Tolerância a falhas:** capacidade de continuar funcionando mesmo quando ocorrem problemas.
* **Escalabilidade:** possibilidade de suportar o aumento de usuários e de solicitações.
* **Segurança:** proteção dos dados e dos recursos do sistema.
* **Manutenção e atualização:** facilidade para corrigir erros e implementar melhorias.

## Comunicação entre computadores

A comunicação pode ser representada pela troca de informações entre dois computadores conectados por portas de comunicação.

### Envio de informações

O computador utiliza operações como `send` ou `write` para transmitir dados, que podem ser bytes, textos ou objetos.

Quando um objeto é convertido em uma sequência de bytes para ser transmitido pela rede, ocorre a **serialização**.

### Recebimento de informações

O computador utiliza operações como `receive` ou `read` para receber os dados enviados.

Quando os bytes recebidos são convertidos novamente em um objeto, ocorre a **desserialização**.

## Objetivos da disciplina e utilização de frameworks

Os **frameworks** oferecem estruturas e ferramentas que auxiliam no desenvolvimento de aplicações, incentivando boas práticas, reutilização de código e atualizações frequentes.

Um dos objetivos da disciplina é desenvolver sistemas capazes de permitir a comunicação entre computadores de maneira eficiente, buscando reduzir atrasos e compartilhar informações quase em tempo real.

A proposta é compreender esses mecanismos e aprender a implementar os componentes necessários por meio da programação.

## Threads e programação concorrente

As **threads** são unidades de execução que permitem realizar diferentes tarefas dentro de um programa. Elas utilizam recursos como memória e processador e possuem um ciclo de vida, desde a criação até o encerramento.

### Concorrência e paralelismo

Na **programação concorrente**, várias tarefas podem avançar durante o mesmo período, alternando o uso do processador. Isso não significa necessariamente que sejam executadas simultaneamente.

Já o **paralelismo** ocorre quando diferentes tarefas são executadas efetivamente ao mesmo tempo, por exemplo, utilizando múltiplos núcleos do processador.

### Ciclo de vida das threads

O gerenciamento de threads envolve sua criação, inicialização, controle da execução, sincronização e encerramento.

Uma thread pode ser criada por um processo ou por outra thread. Dependendo da estrutura do programa, pode existir uma relação de dependência entre elas.

### Condições de corrida e seções críticas

Quando diferentes threads acessam e modificam uma mesma região da memória, podem ocorrer **condições de corrida (*race conditions*)**.

Para evitar esse problema, são utilizados mecanismos de sincronização, como **locks**, que controlam o acesso aos dados compartilhados.

As regiões do código que acessam recursos compartilhados e precisam de proteção são chamadas de **seções críticas**.

---

# Aula 2 (31/07/2026) — Revisão de Sistemas Paralelos e Distribuídos

## Sistemas Paralelos

Os sistemas paralelos utilizam recursos computacionais para executar tarefas de maneira simultânea ou coordenada, buscando aumentar o desempenho das aplicações.

### Principais características

* **Padronização:** geralmente utilizam máquinas com hardware, sistemas operacionais e ferramentas de programação semelhantes.
* **Integração física:** os computadores podem estar fortemente conectados, formando uma estrutura integrada de processamento.
* **Comunicação:** a troca de informações ocorre por meio de uma rede, utilizando endereços, portas e protocolos.
* **Organização:** um exemplo comum é o *cluster* computacional, no qual várias máquinas trabalham em conjunto.

### Arquitetura e aspectos importantes

Os sistemas paralelos precisam considerar a comunicação entre as máquinas, a tolerância a falhas, a segurança, a manutenção e a atualização dos componentes.

### Objetivo principal

O propósito é combinar recursos de processamento e memória para executar tarefas com maior eficiência, reduzir o tempo de processamento e lidar com grandes volumes de trabalho.

## Sistemas Distribuídos

Os **sistemas distribuídos** são compostos por computadores independentes que cooperam por meio de uma rede.

Essas máquinas podem possuir hardwares, sistemas operacionais e linguagens de programação diferentes, sendo consideradas **heterogêneas e fracamente acopladas**.

### Principais arquiteturas

* **Cliente-Servidor:** existe um servidor que fornece serviços aos clientes.
* **Ponto a Ponto (P2P):** os participantes podem atuar tanto como solicitantes quanto como fornecedores de recursos.
* **Híbrida:** combina características dos modelos anteriores.

### Principais desafios

Os sistemas distribuídos precisam lidar com diferentes dificuldades:

* **Tolerância a falhas:** manter os serviços funcionando diante de problemas.
* **Escalabilidade:** permitir o crescimento da infraestrutura.
* **Segurança:** proteger os dados e as comunicações.
* **Sincronização:** coordenar as operações realizadas por diferentes computadores.
* **Sincronização de relógios:** lidar com diferenças de tempo entre as máquinas.
* **Exclusão mútua:** impedir acessos conflitantes a recursos compartilhados.

## Comunicação e utilização de threads

### Sockets

Os **sockets** permitem a troca de dados entre aplicações conectadas por uma rede.

Algumas operações de leitura e escrita são bloqueantes, ou seja, a execução pode ficar aguardando a chegada ou o envio de informações.

### Threads

As threads ajudam a lidar com essas esperas, permitindo que outras tarefas sejam executadas enquanto uma operação de comunicação permanece bloqueada.

### Threads com compartilhamento de memória

Quando diferentes threads acessam os mesmos dados, é necessário utilizar mecanismos de sincronização para evitar condições de corrida.

Em Java, podem ser utilizadas técnicas com `Runnable`, além de recursos de controle de acesso aos dados compartilhados.

### Execuções com dados independentes

Quando cada tarefa trabalha com seus próprios dados, a necessidade de sincronização entre elas tende a ser menor.

Em Java, a classe `Thread` pode ser utilizada para criar essas execuções independentes.

---

# Aula 3 (03/08/2026) — Ausência na Aula

Não foi possível comparecer à aula por motivo pessoal.

Nesse encontro, o professor começou a apresentar exemplos práticos em **Python**, demonstrando os conceitos de comunicação e execução concorrente estudados nas aulas anteriores.

---

# Aula 4 (07/08/2026) — Continuação de Threads em Python

## Arquitetura Cliente-Servidor

O modelo cliente-servidor centraliza determinados serviços em um servidor responsável por receber solicitações e enviar respostas aos computadores clientes.

### Vantagens e desvantagens

A centralização facilita a administração, a organização e o controle das operações. Entretanto, se o servidor principal apresentar uma falha, os serviços que dependem dele poderão ficar indisponíveis.

## Arquitetura Ponto a Ponto (P2P)

Na arquitetura P2P, não existe necessariamente um servidor central responsável por toda a comunicação. Os próprios computadores podem compartilhar informações e recursos diretamente.

Um exemplo desse funcionamento é o **BitTorrent**, no qual os participantes podem receber e disponibilizar partes de arquivos.

### Principais vantagens

* Distribuição das responsabilidades entre os participantes;
* Possibilidade de expansão da rede;
* Compartilhamento direto de recursos;
* Menor dependência de um único computador.

Assim, a saída de um participante não significa necessariamente que toda a rede deixará de funcionar.

## Comunicação em sistemas distribuídos

A comunicação permite que os computadores troquem mensagens e cooperem para executar determinadas tarefas.

Esse processo pode enfrentar problemas como atrasos na transmissão, perda de mensagens, falhas de conexão e indisponibilidade de participantes.

Por isso, os sistemas precisam ser preparados para lidar com essas situações e manter a comunicação tão eficiente quanto possível.

## Sincronização entre máquinas

A **sincronização** organiza a execução das tarefas e ajuda a impedir que operações conflitantes comprometam os dados.

Um exemplo ocorre quando dois computadores tentam modificar o mesmo registro ao mesmo tempo. Sem um controle adequado, o resultado pode ser inconsistente.

Como os computadores distribuídos não possuem necessariamente relógios perfeitamente sincronizados, são utilizados mecanismos de coordenação, relógios lógicos e algoritmos de consenso.

Um exemplo é o **Raft**, algoritmo utilizado para auxiliar na obtenção de consenso entre participantes de um sistema distribuído.

---

# Aula 7 (17/08/2026) — Primeiro Trabalho Prático

## Exercício 1: Caixas de Evento — Compartilhamento de Memória

### Objetivo

Simular cinco threads responsáveis por registrar vendas em uma variável central chamada `saldo_central`.

Cada thread deverá contabilizar mil vendas, sendo que cada venda possui o valor de **R$ 10,00**.

Como são cinco threads, o total será de cinco mil vendas.

### Cuidados necessários

Todas as threads atualizam a mesma variável. Por isso, é necessário utilizar mecanismos de sincronização para evitar condições de corrida e garantir que os valores sejam somados corretamente.

### Resultado esperado

**R$ 50.000,00.**

## Exercício 2: Relatório de Filiais — Sem Compartilhamento de Memória

### Objetivo

Criar quatro threads que representem quatro filiais diferentes. Cada uma receberá uma lista própria de vendas e calculará seu total individualmente.

Como as listas são independentes, cada thread poderá realizar sua soma sem modificar diretamente os dados das demais filiais.

### Funcionamento

1. Cada thread recebe os dados de uma filial.
2. Cada uma calcula a soma das vendas de sua própria lista.
3. A thread principal utiliza o método `join()` para aguardar o término das quatro threads.
4. Após a conclusão de todas elas, os resultados individuais são reunidos para calcular o total geral.

### Resultado esperado

**A soma dos valores calculados pelas quatro filiais.**

---

# Aula 8 (24/08/2026) — Revisão para a Prova

Foi realizada uma revisão dos conteúdos estudados durante as aulas anteriores, com o objetivo de retomar os conceitos principais e esclarecer dúvidas antes da avaliação teórica prevista para sexta-feira.

---

# Aula 9 (28/08/2026) — Primeira Prova

Foi realizada a primeira avaliação teórica da disciplina, envolvendo os conteúdos estudados até aquele momento.

---

# Aula 10 (31/08/2026) — Discussão sobre a Prova e Introdução aos Sockets

## Discussão da avaliação

Durante a aula, foram discutidas as questões da prova e esclarecidas as respostas esperadas pelo professor.

A questão que apresentou maior dificuldade foi a última, relacionada aos mecanismos necessários para garantir a **exclusão mútua**.

Na discussão, foram mencionados conceitos como **sincronização, locks e controle de acesso às seções críticas**, que são utilizados para impedir que diferentes threads acessem simultaneamente um recurso compartilhado de maneira inadequada.

## Introdução aos sockets

Após a análise da avaliação, iniciou-se o estudo dos **sockets**, mecanismos que permitem estabelecer a comunicação entre programas por meio de uma rede.

---

# Aula 11 (04/09/2026) — ServerSocket e Comunicação Cliente-Servidor

## Introdução ao ServerSocket

A aula apresentou o funcionamento do `ServerSocket`, utilizado em Java para criar um servidor capaz de aguardar e aceitar conexões de clientes por meio do protocolo TCP.

Foi abordada uma estrutura inicial de comunicação **um para um (1:1)**, na qual um cliente se conecta ao servidor para trocar informações.

## Desenvolvimento de um mini chat

Também foi introduzida a proposta de desenvolver um pequeno sistema de conversa, semelhante a um chat, utilizando o terminal como interface.

A aplicação deverá permitir que os participantes enviem e recebam mensagens por meio da comunicação entre cliente e servidor.

---

# Aula 14 (25/09/2026) — Comunicador UDP e Geração de Tokens

## Comunicação utilizando UDP

O **UDP (*User Datagram Protocol*)** é um protocolo de transporte que permite enviar e receber dados pela rede.

Assim como o TCP, pode ser utilizado para transmitir informações entre aplicações, inclusive textos e dados de objetos serializados.

### Principal diferença entre TCP e UDP

A principal diferença é que o UDP **não estabelece previamente uma conexão** entre os participantes antes de enviar os dados.

Isso reduz certas etapas da comunicação, mas não garante que os pacotes sejam entregues, cheguem na ordem correta ou sejam recebidos apenas uma vez.

## Autenticador semelhante ao Google Authenticator

Foi apresentado um mecanismo de autenticação baseado em **tokens temporários**, semelhantes aos utilizados pelo Google Authenticator.

Nesse modelo, o servidor utiliza o tempo como referência para gerar ou validar códigos que permanecem válidos por um período limitado.

A cada intervalo determinado, um novo código passa a ser utilizado. Quando um usuário solicita seu token, o sistema retorna o código atual correspondente àquele usuário e ao período de validade.

A renovação periódica dos tokens contribui para a segurança, pois limita o tempo durante o qual cada código pode ser utilizado.

## Exercício: Sistema de cadastro de usuários e geração de tokens via UDP

### Objetivo

Desenvolver um servidor que ofereça dois serviços principais: cadastro de usuários e geração ou consulta de tokens temporários por meio da comunicação UDP.

### 1. Cadastro de usuários

O sistema deverá permitir registrar usuários e armazenar as seguintes informações:

* **Nome:** identificação do usuário;
* **E-mail:** endereço eletrônico associado à conta;
* **Token atual:** código temporário utilizado na autenticação.

### 2. Geração e consulta de tokens UDP

O servidor deverá atualizar o token de cada usuário a cada **60 segundos**.

Quando um usuário realizar uma solicitação, o sistema deverá responder com o token atual e válido correspondente àquele usuário.

O código poderá ser gerado utilizando um número aleatório, sem a necessidade de utilizar o método `hashCode()`.

### Exemplo de funcionamento

**Cadastro inicial:**

* **Nome:** João
* **E-mail:** joao...
* **Token atual:** 483921

**Após 60 segundos:**

* **Nome:** João
* **E-mail:** joao...
* **Novo token:** 726154

### Resultado esperado

O exercício deverá reunir os conceitos de **cadastro de usuários, comunicação por sockets UDP, controle de tempo e atualização periódica de informações no servidor**.
