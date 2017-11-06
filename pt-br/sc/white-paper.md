## 1. Prefácio

Por *"smart contracts"* entendemos qualquer programa de computador que possa executar automaticamente os seus termos pré-programados, como cláusulas de um contrato. A ideia de *smart contract* foi proposta pela primeira vez pelo criptógrafo Nick Szabo, em 1994, sendo tão antiga quanto a própria Internet. Devido à falta de um ambiente de execução confiável, os *smart contracts* não foram amplamente utilizados.

Em 2008, um homem sob o nome de Satoshi Nakamoto lançou o Bitcoin e delineou os conceitos fundamentais de uma *blockchain*. Dentro da *blockchain* do Bitcoin, Nakamoto utiliza um conjunto de linguagens para ajudar os usuários a ter mais flexibilidade no controle de suas contas pessoais e do processo de transferência, o que eventualmente se tornou a forma embrionária de um sistema de *smart contracts* para *blockchain*.

Em 2014, um adolescente chamado Vitalik Buterin lançou o Ethereum, que fornece um sistema de *smart contracts*, Turing-completo, que pode ser usado para criar uma variedade de aplicações descentralizadas para *blockchain*.

A *blockchain* NEO compreende tanto um recurso digital quanto uma plataforma de aplicativos, que fornece um novo e exclusivo sistema de *smart contracts*, o NeoContract. No cerne da plataforma Neo, são fornecidas funções como recursos de ativos digitais (NeoAsset) e de identidade digital (NeoID), o que permite que os usuários se envolvam facilmente em negócios digitais e não se limitam apenas à emissão de tokens nativos da rede.

Este artigo irá introduzir recursos do NeoContract e explorar detalhes não-técnicos. Consulte a [documentação técnica](http://docs.neo.org) para outra abordagem.

## 2. Recursos

### 2.1 Certeza

Se um programa estiver sendo executado em computadores diferentes ou em momentos diferentes no mesmo computador, o comportamento do programa é dito *determinístico* se uma mesma entrada for garantia para gerar uma mesma saída e vice-versa.

A *blockchain* é um armazenamento multipartidário, e um método computacional, tais quais que os dados neste sistema distribuído são resultado de cálculos confiáveis e que não podem ser adulterados. Os *smart contracts* operam nos vários nós dessa rede distribuída da *blockchain*. Se um *smart contract* não for determinístico, os resultados de diferentes nós podem ser inconsistentes. Como resultado, o consenso entre os nós não pode ser alcançado e a rede para. Portanto, na concepção de um sistema de *smart contract*, é necessário eliminar quaisquer fatores que possam levar a comportamentos não determinísticos.

#### 2.1.1 Tempo

A obtenção do tempo (dia, mês, hora, etc) do sistema é uma função de sistema muito comum, que pode ser fortemente aplicada em determinados procedimentos de contratos sensíveis ao tempo. No entanto, a obtenção do tempo do sistema é uma função de sistema não determinística. Além disso, é difícil obter um tempo unificado e preciso em um sistema distribuído, pois os resultados de diferentes nós serão inconsistentes. O NeoContract fornece uma função de sistema baseada em bloco que trata toda a *blockchain* como um servidor de *timestamps* e obtém o *timestamp* sempre que um novo bloco é gerado. Em média, a rede NEO gera um novo bloco a cada 15 segundos, de modo que o *smart contract* é executado aproximadamente ao mesmo tempo que a geração de bloco, ou seja, durante um período de mais ou menos 15 segundos.

#### 2.1.2 Aleatoriedade

Muitos programas de *smart contracts*, como *game contracts*, usam funções de números aleatórios. No entanto, a geração de número aleatório é uma função tipicamente não determinística, em que cada execução do sistema obterá um resultado diferente. Em um sistema distribuído, existem várias maneiras de resolver esse problema: Em primeiro lugar, a mesma semente (do algoritmo de geração de número aleatório) pode ser usada para todos os nós, de modo que o resultado de toda a função aleatória seja determinística. Porém, este método expõe o resultado aleatório completo com antecedência (sabendo a entrada, pode-se prever a saída), reduzindo consideravelmente o valor prático do número "aleatório". Outra solução possível é permitir que todos os nós se comuniquem de forma colaborativa para gerar números aleatórios. Isto pode ser conseguido com o uso de técnicas criptográficas para produzir um número aleatório válido, mas a desvantagem neste caso está no baixo desempenho do processo e necessidade de carga extra de comunicação. Um provedor de números aleatórios centralizado pode ser usado para gerar números aleatórios que garantem consistência e desempenho, mas a desvantagem desta abordagem é óbvia; Os usuários terão de confiar incondicionalmente no provedor centralizado.

Existem duas maneiras de gerar um número aleatório na rede NEO:

1. Quando cada bloco é gerado, o campo Nonce do novo bloco é preenchido com um número aleatório. O programa de *smart contract* pode então facilmente obter o número aleatório de qualquer bloco fazendo referência ao campo Nonce

2. O programa de *smart contract* pode usar o valor da *hash* do bloco como um gerador de números aleatórios, porque o valor da *hash* do bloco possui certa aleatoriedade inerente. Este método pode ser usado para obter um número aleatório fraco

#### 2.1.3 Fonte dos Dados

Se um programa obtém dados no *runtime*, ele pode se tornar um programa não determinístico dependendo da fonte dos dados. Por exemplo, usando diferentes mecanismos de busca para obter os 10 melhores resultados de pesquisa de uma determinada palavra-chave, podem ser produzidos resultados diferentes, em diferentes ordens de classificação, se forem usados ​​diferentes endereços IP em cada busca.

Para *smart contracts* a NEO fornece dois tipos de fontes de dados determinísticos:


1. **Registro da _Blockchain_**

    Através de serviços interoperáveis, o *smart contract* pode acessar todos os dados da *blockchain*, incluindo blocos completos e transações, e cada um de seus campos. Os dados nos blocos são determinísticos e consistentes, de forma que podem ser utilizados por *smart contracts*.


2. **Armazenamento Privado do _Smart Contract_**

   Cada contrato implementado na rede NEO possui uma área de armazenamento privativa que só pode ser acessada pelo script do próprio contrato. O mecanismo de consenso NEO assegura a consistência do armazenamento de cada nó na rede.

Para situações em que seja necessário acessar dados fora da *blockchain*, não há nenhuma maneira direta de fazê-lo. Os dados fora da *blockchain* terão de ser transferidos para a *blockchain* NEO através de transações e em seguida terão de ser traduzidos para alguma das fontes previamente mencionadas, para só então serem acessíveis aos *smart contracts*.


#### 2.1.4 Chamada de Smart Contract

Os contratos no NeoContract podem chamar uns aos outros, mas não podem ser chamados recursivamente. A recursão pode ser efetuada dentro de um mesmo contrato, mas não pode atravessar os limites de tal contrato. Além disso, a chamada entre contratos deve ser estática: o destino não pode ser especificado durante o *runtime*. Isso permite que o comportamento do programa seja totalmente determinado, e sua chamada seja totalmente definida, antes que ele possa ser executado. A partir disso, vários contratos podem ser particionados dinamicamente e executados paralelamente.

### 2.2 Alta Performance

O ambiente de execução de um *smart contract* tem papel fundamental em sua performance. Quando analisamos o desempenho do ambiente de execução, dois indicadores se mostram críticos:

1. Velocidade de execução das instruções
2. Velocidade de inicialização do próprio ambiente de execução

Para *smart contracts*, a velocidade de inicialização do ambiente geralmente é mais importante do que a velocidade de execução das instruções, até porque, a implementação das instruções pode ser facilmente otimizada. Toda vez que um *smart contract* é invocado, ele precisa inicializar uma nova máquina/container virtual. Portanto, a velocidade de execução do próprio ambiente (cada vez que inicia uma máquina/container virtual) tem maior impacto no desempenho do sistema.

O NEO utiliza a NeoVM (NEO Virtual Machine) como ambiente de execução de *smart contracts*. A NeoVM tem inicialização muito rápida e baixíssimo consumo de recursos, sendo perfeita para programas curtos, como são os *smart contracts*. O uso de Hotspot e compilação de *smart contracts* com *JIT* (compilador em tempo real) pode melhorar significativamente a eficiência da máquina virtual.


### 2.3 Escalabilidade

#### 2.3.1 Particionamento Simultâneo e Dinâmico

A escalabilidade de um sistema envolve duas áreas principais: escala vertical e escala horizontal. A escalabilidade vertical refere-se à otimização do fluxo de trabalho de processamento, permitindo que o sistema aproveite ao máximo a capacidade do equipamento existente. Com esta abordagem, os limites do sistema são facilmente alcançados, uma vez que a capacidade de processamento em série é baseada no limite de hardware de um único dispositivo. Quando precisamos escalar além deste ponto, como transformar o sistema em série em um sistema paralelo? Teoricamente, só precisamos aumentar o número de dispositivos, e poderemos alcançar uma escalabilidade quase ilimitada. Poderíamos atingir escalabilidade ilimitada em sistemas distribuídos como a *blockchain*? Em outras palavras, a *blockchain* é capaz de executar programas (*smart contracts*) em paralelo?

Como já discutido, a *blockchain* é um registro, ou livro-razão, distribuído, que registra uma variedade de dados de estado e as regras que regem as mudanças no estado desses dados. *Smart contracts* são usados ​​como operadoras, para registrar essas regras. A *blockchain* poderá processar programas em paralelo somente se múltiplos *smart contracts* puderem ser executados simultaneamente e de maneira não sequencial. Basicamente, se os *smart contracts* não interagem uns com os outros, ou se o *smart contract* não modifica os mesmos dados de estado ao mesmo tempo, sua execução não é seqüencial e pode ser executada simultaneamente. Caso contrário, ele só pode ser executado em série, seguindo uma ordem seqüencial, e a rede não pode escalar horizontalmente.

Com base na análise acima, podemos facilmente projetar "escalabilidade ilimitada" em sistemas de *smart contracts*. Tudo o que devemos fazer é configurar e garantir as regras simples:

  - **Um *smart contract* só pode modificar o registro de estado do contrato ao qual ele pertence**
  - **No mesmo lote de transações (bloco), cada contrato só pode ser executado uma vez**

Como resultado, todos os *smart contracts* podem ser processados ​​em paralelo, uma vez que a ordem seqüencial é irrelevante para o resultado. No entanto, se "*um smart contract só pode modificar o registro de estado do contrato ao qual ele pertence"*, isso implica que os contratos não podem chamar uns aos outros. Cada contrato é uma ilha isolada; se *"no mesmo lote bloco de transações, cada contrato só pode ser executado uma vez"*, isso implica que um ativo digital emitido com um *smart contract* só suporta uma transação por bloco. Este é um mundo de diferenças em relação aos objetivos originais para os *smart contracts*, que assim deixam de ser "*smarts*". Nossos objetivos incluem chamadas mútuas entre *smart contracts* e possível execução múltipla de uma mesma chamada em um mesmo bloco.

Felizmente, os *smart contracts* no NEO são invocados por chamadas estáticas em que o destino da chamada não pode ser especificado/alterado durante o *runtime*. Isso permite que o comportamento do programa seja totalmente determinado, e sua chamada seja totalmente definida, antes que ele possa ser executado. Exigimos que cada contrato indique explicitamente os contratos que provavelmente serão invocados, de modo que o ambiente operacional possa, antes de executar o contrato, calcular toda a árvore de processo e com base nisso particionar a execução dos contratos. Contratos que podem modificar o mesmo registro de estado são executados de forma seqüencial dentro da mesma partição, de modo que diferentes partições possam, então, ser executadas em paralelo.

#### 2.3.2 Baixo Acoplamento

Acoplamento é uma medida da dependência entre duas ou mais entidades. O sistema NeoContract tem um design de baixo acoplamento, que é executado na NeoVM, e que se comunica com dados de fora da *blockchain* através de serviços interoperáveis. Como resultado, a maioria dos *upgrades* em funções de *smart contracts* podem ser feitos através da API destes serviços interoperáveis.


## 3. Uso do *Smart Contract*

### 3.1 Contrato de Verificação

Ao contrário do Bitcoin, que utiliza um sistema de conta baseado em uma chave pública, o NEO utiliza um sistema  baseado em *smart contracts*. Cada conta no ecossistema NEO corresponde a um contrato de verificação, e cada *hash* de contrato (de verificação) corresponde ao endereço da conta; A lógica do contrato de verificação controla a propriedade da conta. Ao transferir de uma conta, primeiro você precisa executar o contrato de verificação para essa conta. Um contrato de validação pode aceitar um conjunto de parâmetros (geralmente uma assinatura digital ou outro critério) e retornar um valor booleano após a verificação, indicando o sucesso da verificação no sistema.

O usuário pode implantar o contrato de verificação na *blockchain* ou publicar o conteúdo do contrato diretamente na transação durante o processo de transferência.


### 3.2 Contrato de Aplicação

O contrato de aplicação é desencadeado por uma transação especial, que pode acessar e modificar o estado global do sistema e o estado privado do contrato (área de armazenamento) durante o *run time*. Por exemplo, durante a execução do contrato, você pode criar um ativo digital, votar, salvar dados e até mesmo criar dinamicamente um novo contrato.

A execução do contrato de aplicação possui cobrança por instrução. Quando a tarifa da transação for inteiramente consumida, o contrato falhará e interromperá sua execução, e todas as alterações de estado serão revertidas. O sucesso do contrato não afeta a validade da transação.


### 3.3 Contrato de Função

O contrato de função é usado para fornecer algumas funções públicas ou comumente usadas, que podem ser chamadas por outros *smart contracts*. O código do *smart contract* pode ser reutilizado, para que os desenvolvedores possam escrever lógica de negócios cada vez mais complexa. Cada contrato de função, quando implementado, pode optar ter uma área de armazenamento privada que pode tanto ser lida, quanto gravada em futuros contratos.

O contrato de função deve ser pré-implementado na *blockchain* que o invocará, e ser removido da *blockchain* por uma função "autodestrutiva" que não será mais usada e que terá seu armazenamento privado destruído. Os dados do contrato antigo podem ser migrados automaticamente para outro subcontrato antes de serem destruídos, usando ferramentas de migração de contrato.

## 4. Máquina virtual

### 4.1 Hardware virtual

A NeoVM fornece interface de hardware virtual para dar suporte à execução de *smart contracts*, incluindo:

  - **CPU**

 A CPU é responsável por ler e ordenar sequencialmente a execução das instruções no contrato, de acordo com a função do controle de fluxo, das operações aritméticas e operações lógicas. No futuro, a função da CPU pode ser estendida com a introdução da função JIT (*just in time* - compilador em tempo real), tornando mais eficiente a execução de instruções.

  - **Pilha de Processos**

   A pilha de processos, ou  pilha de chamadas, é usada para manter a informação de contexto do programa a cada chamada de uma função, para que ele continue a ser executado depois que a função for finalizada e retornar.

  - **Pilha de Cálculos**

   A pilha de cálculo armazena os dados do *run-time* da NeoVM. Após a implementação de instruções diferentes, a pilha será calculada nos elementos de dados correspondentes da operação. Por exemplo, quando operações de adição são executadas, as duas partes da adição são ejetadas da pilha de cálculo e o resultado da adição é inserido no topo da pilha. Os parâmetros de chamada de função também devem ser calculados da direita para a esquerda, de acordo com a ordem da pilha. Depois que a função é executada com sucesso, o topo da função de busca da pilha retorna o valor.

  - **Pilha de Reposição**

  Quando você precisa agendar ou reorganizar elementos na pilha, você pode armazenar temporariamente os elementos na pilha de reposição para recuperá-los no futuro.

### 4.2 Conjunto de instruções

A NeoVM fornece um conjunto de instruções simples e práticas para o desenvolvimento de programas de *smart contracts*. De acordo com as funções, as categorias principais são as seguintes:

- Instrução de constante
- Instrução de controle de processo
- Instrução de manipulação da pilha
- Instrução de string
- Instrução lógica
- Instrução de operação aritmética
- Instrução criptográfica
- Instrução de manipulação de dados

Vale ressaltar que o conjunto de instruções NeoVM fornece uma série de instruções criptográficas, como ECDSA, SHA e outros algoritmos para otimizar a eficiência de implementação de algoritmos criptográficos em *smart contracts*. Além disso, as instruções de manipulação de dados suportam diretamente arrays e estruturas de dados complexas.

### 4.3 Interface de Serviço Interoperável

A máquina virtual onde o *smart contract* é executado é um ambiente *sandbox* e requer uma interface de serviço interoperável para acessar dados fora do *sandbox* ou para manter persistentes os dados do *run-time*. Na interface, o NEOContract pode abrir uma série de funções e serviços do sistema com o programa de *smart contract*, e esses contratos podem ser chamados e acessados como funções comuns. Todas as funções do sistema são realizadas simultaneamente, portanto, não há necessidade de se preocupar com a escalabilidade.

### 4.4 Função de Depuração

Muitas vezes o desenvolvimento de *smart contracts* é dificultado devido à falta de bons métodos de depuração e teste. A NeoVM fornece suporte à depuração do programa em nível da máquina virtual, onde você pode definir o ponto de interrupção no código do contrato ou na execução de um único processo. Graças ao design de baixo acoplamento entre a máquina virtual e a *blockchain*, é fácil integrar a NeoVM diretamente com vários IDEs para fornecer um ambiente de teste consistente com o ambiente de produção final.

## 5. Linguagens de Alto Nível


### 5.1 C#, VB.Net, F#

Desenvolvedores podem usar o NeoContract com uma gama variada de linguagens alto nível. As primeiras linguagens suportadas são C#, VB.Net, F#. Fornecemos compiladores e plugins para essas linguagens, permitindo a sua compilação no conjunto de instruções suportado pela NeoVM. Como o compilador NEO é para MSIL (linguagem intermediária da Microsoft), teoricamente qualquer linguagem .NET e qualquer linguagem que possa ser traduzida para MSIL será automaticamente suportada.

Um grande número de desenvolvedores é proficiente nessas linguagens, as quais possuem IDEs muito fortes. Os desenvolvedores podem desenvolver, gerar, testar e depurar, tudo no Visual Studio, onde eles são capazes de tirar o máximo proveito dos modelos de desenvolvimento de *smart contracts* que fornecemos.

### 5.2 Java, Kotlin

Java e Kotlin formam o segundo lote de linguagens suportadas, para as quais fornecemos compiladores e plugins IDE, viabilizando a utilização de linguagem baseada em JVM no desenvolvimento de aplicativos de Smart Contracts da NEO.

O Java é amplamente utilizado, e recentemente Kotlin se tornou a linguagem oficial para desenvolvimento Android recomendado pela Google. Acreditamos que dar suporte a essas linguagens ajudará a aumentar drasticamente o número de desenvolvedores de *smart contracts* NEO.


### 5.3 Outras Liguagens

Posteriormente, o NeoContract irá adicionar suporte para outras linguagens alto nível, com base no grau de dificuldade e no processo de desenvolvimento do compilador. Algumas das linguagens que poderão ser suportadas incluem:

  - C, C++, GO
  - Python, JavaScript

No futuro, continuaremos a adicionar suporte a linguagens alto nível. Nosso objetivo é ver mais de 90% dos desenvolvedores NEO desenvolvendo com o NeoContract sem precisar aprender uma nova linguagem.

## 6. Serviço

### 6.1 Registro Blockchain

Informações dos blocos da *blockchain* NEO, incluindo blocos completos e transações, e cada um de seus campos, podem ser acessadas, através das funções do sistema fornecidas pelo serviço interoperável. Especificamente, você pode consultar os seguintes dados:
	- Altura (tamanho) da *blockchain*
	- Cabeçalho de bloco, bloco atual
	- Transações
	- Tipo de transação, atributos, entrada, saída, etc.

Através destes dados, você pode desenvolver algumas aplicações interessantes, como pagamentos automáticos, contratos inteligentes com base na prova da carga de trabalho, etc.

### 6.2 Ativos Digitais

Através dos serviços interoperáveis ​​fornecidos pela interface de ativos digitais, os *smart contracts* não só podem consultar a *blockchain* NEO sobre propriedades e estatísticas de ativos digitais, mas também criar novos ativos digitais durante o *runtime*. Os ativos digitais criados por *smart contracts* podem ser emitidos, transferidos, negociados fora do contrato. Eles são iguais aos ativos nativos da NEO (NEO e GAS) e podem ser gerenciados com qualquer software de carteira compatível com NEO. Esta interface específica inclui:
	- Solicitação de atributos
	- Consulta de estatísticas de ativos
	- Gerenciamento do ciclo de vida do recurso: crie, modifique, destrua, etc.
	- Gerenciamento de ativos: nome multi-idioma, mudança total, alteração de precisão, mudanças no administrador

	
### 6.3 Persistência

Cada programa de *smart contract* implementado na *blockchain* NEO tem uma área de armazenamento privada que só pode ser lida e escrita pelo próprio contrato. Os *smart contracts* possuem permissões operacionais completas dos dados de seu armazenamento próprio: podem ser lidos, escritos, modificados, excluídos. Os dados são armazenados na forma de pares de valores-chave com as seguintes interfaces:
	- Percorrer todos os registros armazenados
	- Retornar para um registro específico de acordo com a chave especificada
	- Modificar ou escrever novos registros de acordo com a chave especificada
	- Apagar o registro de acordo com a chave especificada

Em geral, um contrato só pode ler e escrever dados de seu armazenamento próprio, com uma exceção: quando um contrato é invocado, o contrato invocado pode acessar o armazenamento próprio do invocador através de uma solicitação entre domínios, desde que o invocador forneça autorização. Além disso, o armazenamento próprio de um sub-contrato que é criado dinamicamente na execução de um contrato, pode ser acessado pelo contrato pai.

As solicitações entre domínios permitem que o NeoContract implemente recursos de bibliotecas ricas, que ofereçam recursos de gerenciamento de dados altamente escaláveis ​​para os invocadores.


## 7. Taxas

### 7.1 Taxa de Implantação

A arquitetura distribuída da NEO fornece alta capacidade de redundância de armazenamento, e o uso desta capacidade não é gratuito. A implantação de um *smart contract* na rede NEO requer o pagamento de uma tarifa, atualmente fixada em 500 GAS, que é coletada pelo sistema e registrada como um ganho de sistema. As taxas futuras serão ajustadas de acordo com o custo operacional real no sistema. O *smart contract* implementado na *blockchain* pode ser usado várias vezes, até que o contrato seja destruído pelo implementador.

### 7.2 Taxa de Execução

O NEO fornece um ambiente de execução confiável para *smart contracts* e a execução dos *smart contracts* consome recursos computacionais de cada nó, portanto os usuários devem pagar pela execução de *smart contracts*. A taxa é determinada pelos recursos computacionais consumidos em cada execução e o preço unitário também é em GAS. Se a execução completa do *smart contract* falhar devido à falta de GAS, o custo consumido não será retornado e isso evita ataques maliciosos ao consumo de energia da rede.

A maioria dos contratos simples podem ser executados gratuitamente, desde que os custos de execução permaneçam abaixo de 10 GAS, reduzindo assim os custos para o usuário.

## 8. Cenários de Aplicação

### 8.1 Transações Supercondutoras

Os ativos digitais na *blockchain* exigem inerentemente alguma forma de liquidez e, geralmente, as transações P2P não podem fornecer liquidez suficiente. Portanto, há necessidade de intercâmbio para fornecer aos usuários serviços de negociação. De forma geral, as trocas de ativos digitais podem ser divididas em duas categorias:

1. **Intercâmbio Centralizado:** o usuário precisa depositar os ativos digitais com a troca, e subsequente posição de pedido pendente de negociação
2. **Intercâmbio Descentralizado:** seu sistema de negociação é incorporado na *blockchain*, e o sistema fornece os serviços de correspondência

O *Intercâmbio Centralizado* pode fornecer serviços diversificados e de alto desempenho, mas precisa ter uma forte garantia de crédito, caso contrário, haverá riscos morais; como a apropriação indevida de fundos de usuários, fraude, etc. Comparativamente, o *Intercâmbio Descentralizado* não possui riscos morais, mas a experiência do usuário é fraca e existe maior gargalo de desempenho. Existe uma maneira de combinar ambas as soluções e alcançar o melhor dos dois mundos?

A *"transação supercondutora"* é um mecanismo que pode fazer isso; Os usuários não precisam depositar ativos, onde eles são capazes de usar na negociação seus próprios ativos na *blockchain*. A liquidação de transações é concluída na *blockchain*, mas o processo de correspondência de transações ocorre fora da *blockchain*, por uma "intercambiadora" centralizada que fornece serviços de correspondência. Uma vez que a correspondência é realizada fora da *blockchain*, sua eficiência é como a de um intercâmbio centralizado, mas os ativos permanecem sob o controle do usuário. As movimentações usam a intenção comercial do usuário para realizar serviços de correspondência sem riscos morais envolvidos, como a apropriação indevida de fundos de usuários, fraude, etc.

Atualmente, dentro da comunidade NEO, surgiu o desenvolvimento de *smart contracts* para alcançar transações supercondutoras na *blockchain*, como OTCGO.


### 8.2 *Smart Fund* - Fundo Inteligente

Os *smart funds* baseados na *blockchain* têm o benefício de serem descentralizados, abertos e transparentes, possuindo um maior grau de segurança e liberdade em comparação com os fundos tradicionais. Esses *smart funds* também são transfronteiriços e abertos a investidores, em que projetos destacados podem ser financiados com capital de todo o mundo.

O **Nest** é um projeto de *smart fund* baseado no NeoContract, que é muito semelhante ao projeto TheDAO baseado em Ethereum, em que são necessárias medidas de segurança aprimoradas para evitar os erros da TheDAO (hackers).

### 8.3 Interoperabilidade Entre *Blockchains*

Em um futuro próximo haverá muitas *blockchains* públicas e milhares de *blockchains* de alianças ou privadas existentes em todo o mundo. Esses sistemas de *blockchains* isolados são ilhas de valor e de informação, que não são interoperáveis ​​entre si. Através do mecanismo de __interoperabilidade entre *blockchains*__, várias *blockchains* isoladas podem ser vinculadas, de modo que os valores possam ser trocados entre si para alcançar o verdadeiro valor da Internet.

O NeoContract fornece suporte para a implementação de interoperabilidade entre *blockchains*, garantindo consistência na movimentação de ativos, transações distribuídas e execução de *smart contracts* entre diferentes *blockchains*.
