---
share: true
---
# Hierarquia de memoria
![[Pasted image 20240331233136.png|Pasted image 20240331233136.png]]

---
# Como as informações são processadas

Este é um layout com o qual todos estamos familiarizados. É o layout de computador mais básico que sacrifica alguns detalhes para facilitar o entendimento.

![[Pasted image 20240331234528.png|Pasted image 20240331234528.png]]

O fluxo de dados chega como entrada dos dispositivos e vai direto para a memória, que é representada pela Unidade de Armazenamento. É aqui que começa a maior parte da confusão relacionada a como a memória é usada e o que há dentro dela. Vamos dar uma olhada nisso.

1. Armazenamento primário
2. Armazenamento secundário

Na computação, um dispositivo usado para armazenar informações para uso imediato em um computador ou dispositivo de hardware de computador relacionado é comumente chamado de memória. Normalmente se refere à memória semicondutora onde os dados são armazenados em células de memória semicondutoras de óxido metálico (MOS) em um chip de circuito integrado de silício.

O termo “memória” é frequentemente uma abreviação coloquial do termo “armazenamento primário”. O armazenamento secundário ou memória é frequentemente chamado de “armazenamento”.

As duas “memórias” do processador, que estão alojadas dentro da ==Unidade Central de Processamento (CPU)== são Registros e Cache. Embora sejam uma espécie de memória, geralmente são estudados fora do sistema de memória. Esses são os acessos de memória mais caros e mais rápidos à CPU. Vamos dar uma olhada neles primeiro.

---
# A memória da CPU
## Registros

Registradores são pequenos locais de armazenamento usados pela CPU para armazenar dados e instruções. Eles estão integrados ao próprio processador. Conseqüentemente, esses locais de memória podem ser acessados ​​diretamente pelo processador. Isso os torna a memória acessível mais rápida. Os registros são medidos pelo número de bits que podem conter, por exemplo, um “registro de 8 bits”, “registro de 32 bits” ou um “registro de 64 bits”. 32 bits e 64 bits são comumente usados para descrever a arquitetura ou o design do processador. Um processador de 32 bits possui um registro de 32 bits, que pode armazenar 232 ou 4.294.967.296 valores. Um processador de 64 bits possui um registro de 64 bits, que pode armazenar 264 ou 18.446.744.073.709.551.616 valores.

Se você já se perguntou, ao instalar o software, qual a diferença entre as versões de 32 e 64 bits, agora você sabe.
## Memória cache

A memória cache não é uma memória _original_, mas uma cópia de algumas partes da “Memória Principal” que é usada com frequência. Portanto, o cache é uma memória menor e mais rápida, localizada mais próxima do núcleo do processador, que armazena cópias dos dados da memória principal usada com frequência. Ao tentar ler ou gravar em um local da memória principal, o processador primeiro verifica se os dados desse local já estão no cache. Nesse caso, o processador lerá ou gravará no cache em vez da memória principal, muito mais lenta. Isto ajuda a reduzir o custo médio (tempo ou energia) para acessar dados da memória principal.

As memórias pequenas que estão mais próximas da CPU podem operar mais rápido do que a memória principal, muito maior. A maioria das CPUs desde a década de 1980 usou um ou mais tipos de cache.

Ao tentar ler ou gravar em um local da memória principal, o processador verifica se os dados desse local já estão no cache. Nesse caso, o processador lerá ou gravará no cache em vez da memória principal, muito mais lenta.

Muitas CPUs modernas de desktop, servidores e industriais têm pelo menos três caches independentes:

1. Cache de instruções (I-cache)
     Usado para acelerar a busca de instruções executáveis
2. Cache de dados (cache D)
     Usado para acelerar a busca e armazenamento de dados; o cache de dados geralmente é organizado como uma hierarquia de mais níveis de cache (L1, L2, etc.; veja também caches multiníveis abaixo).
3. Buffer lookaside de tradução (TLB)
     Usado para acelerar a tradução de endereços virtuais para físicos para instruções executáveis e dados. Um único TLB pode ser fornecido para acesso a instruções e dados, ou um TLB de instrução (ITLB) e um TLB de dados (DTLB) separados podem ser fornecidos. No entanto, o cache TLB faz parte da unidade de gerenciamento de memória (MMU) e não está diretamente relacionado aos caches da CPU.

---
# # Memória primária (também conhecida como memória principal, memória interna ou memória principal)

O _armazenamento primário_, muitas vezes referido simplesmente como _memória_, é o único diretamente acessível à CPU. A CPU lê continuamente as instruções armazenadas lá e as executa conforme necessário. Quaisquer dados operados ativamente também são armazenados de maneira uniforme.

Este diagrama detalha tudo. Os dois tipos de memória primária são ROM e RAM.
![[Pasted image 20240401010325.png|Pasted image 20240401010325.png]]
**ROM**: memória somente leitura _(Read Only Memory)_

**RAM**: Memória de acesso aleatório _(Random Acess Memory)_

RAM e ROM são abreviações muito populares, que todo aluno conhece desde o ensino médio, mas posso dizer por mim mesmo que sempre fiquei confuso sobre como elas diferem em forma e funcionalidade. E quando liguei os pontos, fiquei animado. Porque as coisas novas que aprendi sobre eles eram sobre coisas conhecidas, que nunca foram percebidas como são. Então, estou tentando fazer com que você mesmo conecte esses pontos.

Todo mundo sabe que ROM é uma memória somente leitura. Mas por que? Onde esta memória está alojada? Quais funções ele desempenha?
## Memória somente leitura (ROM)

![[Pasted image 20240401011234.png|Pasted image 20240401011234.png]]
[^^] _Cartucho ROM aberto de um Game Boy Color. _

Este é um tipo de _memória não volátil_ usada em computadores e outros dispositivos eletrônicos. Não volátil significa que nenhuma energia é necessária para manter a memória viva. Os dados armazenados na ROM **não** podem ser modificados eletronicamente após a fabricação do dispositivo de memória.

Agora, quase todos os dispositivos vêm com redefinição de fábrica. Portanto, usarei essa analogia para facilitar a compreensão da ROM para você.

A memória do seu computador, que vem embutida nele, quando o computador está sendo fabricado/montado na fábrica, é a ROM. Os dados armazenados na ROM não podem ser alterados e não podem ser modificados facilmente. Conseqüentemente, aquele software que raramente é alterado durante a vida do sistema de computador é armazenado em um dispositivo de memória ROM. Este tipo de software também é conhecido como _Firmware_. (Firmware é um termo muito comum, e computadores ou sistemas semelhantes são redefinidos para ele quando a redefinição de fábrica é aplicada.)

Portanto, pense nisso como a memória ==mais básica== e ==mais importante==. Básico porque você pode **_apenas LER_**, mas **_não pode ESCREVER_** nada nele. Este espaço de memória não está aberto ao usuário. O *BIOS* do seu computador é um exemplo.

Outro exemplo podem ser os cartuchos de videogame, que são plug and play. Eles armazenam o jogo em ROM. Muitos consoles de jogos usam cartuchos ROM intercambiáveis, permitindo que um sistema jogue vários jogos. A ROM vem antes do sistema operacional. ==E permite que o computador tenha seu próprio Firmware.==

_Todo o resto vem depois disso,_ ==_até mesmo o sistema operacional._==
## Mask ROM

![[4go8ave1.bmp|4go8ave1.bmp]]
[^^] _Samsung KM23C4000P-15 4M-Bit (512Kx8) CMOS MASK ROM 32Pin P DIP OMA037D_

A primeira ROM foi conectada. Eles eram compostos de componentes eletrônicos como _[[Diodos|Diodos]]_ ou _[[Circuitos Integrados (CIs)|Circuitos Integrados (CIs)]]_, que ==_não_ podem ser alterados após a fabricação==. Esses CIs ROM também são chamados de Circuitos Integrados Mask ROM. Depois disso, se houver alguma atualização na ROM a ser feita, ela _tem_ que ser substituída. Uma nova ROM com novo firmware atualizado pode ser instalada, mas a ROM antiga e o firmware **_não podem ser alterados._**

Na Mask ROM IC, os dados são codificados fisicamente durante a fabricação. Portanto, só pode ser programado durante a fabricação. Isso cria muitos obstáculos:

1. Como cada Mask ROM é programada durante a fabricação, seu custo se torna muito alto, já que os usuários devem contratar uma fundição para produzir um design customizado. Só é possível encomendar em grandes quantidades.

2. A fabricação de uma ROM é um processo demorado, pois cada ROM é personalizada.

3. Para uso em P&D, onde os usuários precisam fazer tentativa e erro ou modificar e melhorar o conteúdo da memória para refinar um design, o Mask ROM torna-se impraticável.

4. Se a ROM estiver com defeito e o produto for enviado, ele não poderá ser corrigido sem o Total Recall.
## ROM programavel (PROM)

![[qqlqjh58.bmp|qqlqjh58.bmp]]
[^^] _Texas Instruments PROM type TBP18SA030N._

Essas deficiências criaram a necessidade de uma ROM programável (PROM). Estes foram inventados por Wen Tsing Chow em 1956, permitindo aos usuários programar seu conteúdo exatamente uma vez, alterando fisicamente sua estrutura com a aplicação de pulsos de alta tensão. Isso resolveu os problemas 1 e 2 acima, uma vez que uma empresa pode simplesmente encomendar um grande lote de chips PROM novos e programá-los com o conteúdo desejado de acordo com a conveniência de seus projetistas. No entanto, isso também foi possível apenas uma vez.
## ROM programável apagável (EPROM)

![[e8mod6kz.bmp|e8mod6kz.bmp]]
[^^] _Circuitos integrados de memória somente leitura programável apagável (EPROM) em pacotes duplos em linha. Essas embalagens possuem uma janela transparente que mostra a matriz em seu interior. A janela é usada para apagar a memória expondo o chip à luz ultravioleta._

Em 1971, Dov Frohman da _Intel_ inventou a memória somente leitura programável apagável (EPROM). Esta nova ROM, conhecida como EPROM, resolveu essencialmente o terceiro obstáculo da lista acima, uma vez que a EPROM (ao contrário da PROM) pode ser repetidamente redefinida para o seu estado não programado pela exposição a forte luz ultravioleta.
É importante notar que ainda era ==quase impossível para um usuário apagar a ROM _(que é exatamente como pretendido)_== e reescrevê-la. Só resolveu problemas para laboratórios e centros de P&D bem equipados.

![[4tjrzt56.bmp|4tjrzt56.bmp]]
[^^] _A primeira EPROM, uma Intel 1702, com a matriz e as ligações dos fios claramente visíveis através da janela de apagamento._
## ROM programável eletricamente apagável (EEPROM)

![[bqsqovcm.bmp|bqsqovcm.bmp]]
[^^] _STMicro M24C02 I²C serial type EEPROM_

A EEPROM foi desenvolvida por Yasuo Tarui, Yutaka Hayashi e Kiyoko Naga no Laboratório Eletrotécnico em 1972. Isso poderia ser ==programado mesmo em um local remoto== _(usando apenas um computador e cabo serial)._ Isso ajudou a indústria de computação cruzar o quarto obstáculo também. Agora a ROM defeituosa poderia ser reprogramada na casa do consumidor ou usuário, sem a necessidade de levar todo o dispositivo de volta ao fabricante.
## Memória Flash

![[zblw8qdg.bmp|zblw8qdg.bmp]]
[^^] _Uma unidade flash USB desmontada. O chip à esquerda é a memória flash. O controlador está à direita._

No futuro, Fujio Masuoka, da Toshiba, inventou a memória Flash no início dos anos 1980 e a comercializou no final dos anos 1980. ==Memória Flash é uma forma de EEPROM==. Isso usa a área do chip _muito eficientemente_ e pode ser apagado, programado e reprogramado _milhares de vezes_ ==sem qualquer dano==.

Mas um avanço inovador foi que ==agora qualquer parte específica do dispositivo pode ser apagada==. _(ROMs anteriores precisavam ser excluídas na totalidade)_. Isso pode ser feito em alta velocidade, daí o nome “flash”.

Após o advento das Memórias Flash como ROMs, todo o cenário da ROM mudou de “Programável Único” para “Atualização Regular de ROM”. ==O melhor exemplo disso são as atualizações regulares do firmware de vários sistemas de computador.== Anteriormente, o firmware não era fácil de alterar ou atualizar. Agora, em dispositivos móveis, as empresas promovem atualizações remotas do firmware e o usuário baixa e atualiza o mesmo.
## Por que ainda temos EPROM e Mask ROM?

Uma pergunta natural vem à mente: depois de todas as vantagens da EEPROM, por que ainda temos os tipos de ROMs antigos e menos funcionais?

A resposta é simples. **_CUSTO._**

Todas as tecnologias avançadas aumentaram a flexibilidade do chip ROM, mas também há uma desvantagem nisso. A tecnologia tem um custo muito alto por chip. E muitos sistemas não precisam de ROM para atualização durante sua vida útil, tornando desnecessária a carga de custos adicionais. Consequentemente, enquanto a grande quantidade de MASK ROMs for mais barata (economia de escala), elas continuarão sendo a ROM preferida de muitos dispositivos por anos.

---
# Memória de acesso aleatório(RAM)

![[bgnkvtly.bmp|bgnkvtly.bmp]]
[^^] _Exemplo de memória volátil de acesso aleatório gravável: módulos de RAM dinâmica síncrona, usados ​​principalmente como memória principal em computadores pessoais, estações de trabalho e servidores._

**Memória de acesso aleatório** é a _memória volátil_ do computador. Significa que ==esquece tudo o que estava armazenado dentro dele assim que a energia é desligada==. RAM é um “espaço de memória” caro e, portanto, em dispositivos de computação normais, varia de 512 MB a 8 GB _(alguns dispositivos caros, tanto PC quanto móveis, também têm RAM muito maior) _.
Mais quantidade de RAM está associada ao funcionamento mais rápido do computador. A razão para isso pode ser entendida se entendermos como um computador gerencia sua memória interna para operação _(apenas volátil, não ROM)_.

RAM é essencialmente um armazenamento super rápido e de alta velocidade que o computador e seus aplicativos utilizam para armazenar e acessar dados temporários. ==Pode ser considerada como a memória de curto prazo de um computador==. Quando um programa é iniciado _(por exemplo, navegador Google Chrome ou arquivo Microsoft Excel)_, seus dados comuns são armazenados na RAM e, como a RAM é muito mais rápida que um disco rígido _(memória secundária)_, o programa é executado mais rápido por ter dados diretamente acessível da RAM. Assim que o programa termina (você fecha o navegador ou arquivo), a RAM fica livre de seus dados. Conseqüentemente, quanto maior a RAM, mais rápido o computador funciona com maior número de programas simultâneos.

Computadores com menos RAM não conseguem fazer muitas coisas ao mesmo tempo. Digamos, por exemplo, que você esteja trabalhando em vários arquivos de vídeo e, ao mesmo tempo, abra vários navegadores da web. O requisito de RAM aumenta com cada novo programa aberto. O que acontece quando a quantidade necessária de “memória temporária” de um computador excede a RAM? Os computadores modernos usam uma técnica de gerenciamento de memória chamada Memória Virtual.

![[Pasted image 20240401151020.png|Pasted image 20240401151020.png]]
[^^] _A memória virtual combina RAM ativa e memória inativa no DASD[a] para formar uma grande variedade de endereços contíguos._

Este é um método para expandir a capacidade da RAM. Uma parte do disco rígido do computador é reservada para um arquivo de paginação, e agora a soma total da RAM e do arquivo de paginação torna-se a “Memória Temporária” total. No entanto, há um porém. ==O disco rígido é **muito** mais lento que a RAM==. E toda vez que o computador depende da coleta de dados do arquivo de paginação do disco rígido, ele obtém uma resposta mais lenta do que a RAM ofereceria.

Conseqüentemente, quanto maior a RAM, mais rápidas se tornam as operações do computador.

Agora a questão natural surge novamente. Por que a RAM está na faixa de 1 a 8 GB (ou às vezes um pouco mais), mas os discos rígidos estão na faixa de 512 GB a 2 TB _(1 Terabyte = 1024 GB)_?
## Quando a RAM é tão importante, por que não ter uma RAM maior?

A resposta é novamente, **_CUSTO_**.

Os ==dois tipos principais de memória de acesso aleatório volátil são **Memória de acesso aleatório estática (SRAM)** e **Memória de acesso aleatório dinâmica (DRAM)**==. Os usos comerciais de RAM semicondutora remontam a 1965, quando a IBM introduziu o chip SP95 SRAM para seu computador System/360 Modelo 95, e a Toshiba usou células de memória DRAM para sua calculadora eletrônica Toscal BC-1411.
## Memória estática de acesso aleatório (SRAM)

Na RAM estática, os dados são armazenados em uma célula de memória de seis transistores (um tipo de semicondutor) que requer um fluxo constante de energia.
Como o fluxo de energia é constante, não é necessário _atualizar_ a memória para lembrar os dados que estão sendo armazenados. Isso é chamado de estático porque não há necessidade de alteração (nenhuma atualização necessária) para manter os dados intactos. É usado na memória cache.

Isso requer menos energia e oferece acesso e velocidade mais rápidos. Mas, ao mesmo tempo, é menos denso em memória (menos memória no mesmo tamanho) e, portanto, tem um custo mais elevado.
## Memória dinâmica de acesso aleatório (DRAM).

Na RAM dinâmica, os dados são armazenados em células de memória de pares de transistores e capacitores (feitos de metal e não semicondutores). Os capacitores descarregam energia lentamente. E, portanto, os dados (que são armazenados em forma de energia) também são perdidos. Portanto, é necessária uma atualização periódica de energia para mantê-lo funcionando. A DRAM é chamada de dinâmica porque precisa de uma mudança constante de energia (atualização) para manter os dados intactos.

Isso requer maior consumo de energia e acesso mais lento aos dados em comparação com SRAM. Mas, ao mesmo tempo, é mais denso em memória (mais memória no mesmo tamanho) e, portanto, tem um custo menor.

Muitos sistemas de computador possuem uma hierarquia de memória que consiste em registros de processador, caches SRAM on-die, caches externos, DRAM, sistemas de paginação e memória virtual em um disco rígido. Todo esse conjunto de memória pode ser chamado de “RAM”.

---
# Memória Secundária (também conhecida como memória externa ou armazenamento auxiliar):

O armazenamento secundário (também conhecido como memória externa ou armazenamento auxiliar) é diferente do armazenamento primário porque não é acessível diretamente pela CPU. O computador usa seus canais de entrada/saída para acessar o armazenamento secundário e transferir os dados desejados para o armazenamento primário. O armazenamento secundário não é volátil (os dados são retidos mesmo quando a energia é desligada).

![[re7avbjg.bmp|re7avbjg.bmp]]
[^^] _Imagem com vários tipos de mídias de armazenamento._

O tempo de acesso por byte para HDDs ou SSDs é normalmente medido em milissegundos (um milésimo de segundo), enquanto o tempo de acesso por byte para armazenamento primário é medido em nanossegundos (um bilionésimo de segundo). Assim, o armazenamento secundário é significativamente mais lento que o armazenamento primário.

Para mais: [[Different types of media storages|Different types of media storages]]