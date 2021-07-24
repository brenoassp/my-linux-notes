# Linux

#### **Monitorando processos**

Ao usar o computador, independente do sistema operacional utilizado, é importante ter o conhecimento básico de como monitorar os processos que estão sendo executados pelo sistema. Com isso, é possível identificar causas de lentidão no sistema ou até mesmo matar processos indesejados.

Em geral, toda interface gráfica já vem com um monitor de processos instalados, como é o caso do KSysGuard, que é o monitor padrão do KDE Plasma. 

Através do monitor do sistema é possível:

* Ver todos os processos em execução, seu gasto de memória, cpu e usuário que iniciou o processo.
* Enviar um sinal para o processo, por exemplo, pode-se enviar um sinal de kill para matá-lo.
* Monitorar uso de CPU, memória e rede no sistema.

Apesar dos monitores de processo via interface gráfica serem capazes de fazer muito bem o que eles se propõem a fazer, nem sempre é possível utilizá-los pois a interface gráfica pode não estar disponível, como é o caso de quando estamos conectados em uma máquina remota via linha de comando. Nesse caso geralmente utilizamos as ferramentas top ou htop para monitorar o sistema e seus processos.

**Top**

![](https://lh4.googleusercontent.com/BxYAgWFjw0XKSZ1uq2kN8CY8YGHGR7mzQL9XaMpnCHiT5yhVqmsfLnB2iHwFvMMzOuz0pCNXUQRknUCOr240RUaPlatJpNovkRRRdQCDvdBf5-4ovs4qxLsF-_A7lbdEv-y9_VoD)

O top é programa para gerenciar processos via linha de comando e é instalado por padrão na maior parte das distribuições Linux. Existem muitas informações sobre os processos em execução e diferentes possibilidades de configuração nesse programa, mas na grande maioria das vezes estamos apenas interessados em monitorar gasto de memória ou cpu de processos ou até mesmo matar processos que não estão respondendo.

**Informações de CPU**

![](https://lh3.googleusercontent.com/_8aauaOxEYyjbyw8TKrEM0PAZRHcI5nT3V5WVsx6aBs_o2KjwRNYfY3jDeG8UNR4qrqGEU6NSt4lcQDam_n0jxDZvwpqCaXThwmOIqz6LygJ6WUHnokk8W96il2jeqAn0CYtL4yB)

No cabeçalho podemos ver na terceira linha as informações sobre o gasto de CPU pelos processos. Esses valores mostrados em porcentagem representam o gasto de CPU medido pelo top na última atualização feita. Por padrão a atualização ocorre a cada 3 segundos e esse valor pode ser alterado com a tecla \`d\` e fornecendo um novo valor, também em segundos.

Na primeira coluna, 29,9 us indica que essa foi a porcentagem de tempo gasta com processos do usuário que possuem prioridade padrão. Os processos em geral têm prioridade padrão com um valor 0. Valores menores indicam prioridade maior, enquanto valores maiores indicam prioridade menor.

A segunda coluna, 1,6 sis, indica a porcentagem de tempo gasta do CPU com processos do kernel.

A terceira coluna, 36,2 sis, representa o tempo gasto com processos do usuário que possuem prioridade diferente da padrão.

A quarta coluna, 32,2 oc, mostra o tempo ocioso do CPU.

Por fim, as demais colunas, 0,0 ag, 0,0 ih, 0,1 is e 0,0 tr, mostram o tempo gasto aguardando finalizar operações de I/O, tempo gasto servindo interrupções de hardware, tempo gasto servindo interrupções de software e tempo roubado dessa máquina virtual pelo hypervisor, respectivamente.

**Informações de memória**

![](https://lh5.googleusercontent.com/m8s48QU6MoxMlntaAVyuxzWFf5mQiCNw-adVAP0iKYOWR3iE0YOP58viLEpIMO13nPLNoz1BOeSnCDmHzx3qE0IvjEWUnrfAUDwhkAnq7TLdjE5yuXKCRiOJrwG1WwXF3X5krKvX)

Na quarta e quinta linha do cabeçalho vemos informações referentes à memória física e swap, respectivamente. A memória física é o que de fato tem instalado no computador, e a memória swap é utilizada como alternativa à memória física caso a mesma seja totalmente preenchida com os programas em execução no momento. O tamanho da memória swap pode ser configurado a qualquer momento, já que ela nada mais é do que um espaço reservado no disco rígido que poderá ser utilizado como memória RAM. No entanto, é aconselhável monitorar o uso de memória para evitar que isso aconteça pois o disco rígido é significativamente mais lento do que a memória RAM. Ou seja, será nítido que o computador está lento quando começar a usar a swap.

É possível mudar a unidade de medida de memória desse cabeçalho com a letra `E` para facilitar a leitura. Caso queira que essa mudança seja salva para futuras execuções do programa, basta gravar com a tecla `W`.

Nessa parte conseguimos identificar o total de memória livre no sistema, além da memória gasta e utilizada com buffer/cache. Em geral, quando utilizamos o top para identificar a origem de lentidão no sistema, o primeiro passo que damos é olhar a quantidade de memória utilizada e se estamos utilizando a swap.

**Informações de processos**

![](https://lh5.googleusercontent.com/xDX-84fw698Ud4aZ9-tNck6RqI56othBKRBeBOTdtZG6cq-z2Yo0zlkzWvAaIaBmJMihqahijVgTXZxnhZTQjR4nwDdUaYtwka1OqIwgAa1__0T1PgOB_o9m7887Aii_cYPXQVIQ)

Na parte dos processos em execução, existem as seguintes colunas:

**PID:** identificador do processo. É um número inteiro sequencial gerado ao iniciar um novo processo. O responsável por gerar esse identificador e gerenciar os outros processos também é um processo, que possui o PID de valor 1. 

**USUARIO:** usuário que executou o processo.

**PR:** prioridade.

**NI:** valor nice \(niceness\). É um outro tipo de prioridade para o processo. O valor dessa prioridade padrão é 0, podendo variar de **-20 \(prioridade maior\)** a **+19 \(prioridade menor\).**

**VIRT:** tamanho da memória virtual utilizada. 

  **.** top

  . htop t

  . monitor do sistema via interface gráfica

manipulando arquivos

  . cat

  . &gt; &gt;&gt; .

  . nano / vim

  . touch

hierarquia de diretórios

screen  


Distribuições linux. O que muda de uma pra outra?

  . Gerenciador de pacotes. Ex: dpkg, yum, pacman.

  . Kernel

  . Interface gráfica. Ex: gnome, kde, xfce, mate, lxde…

  . Programas instalados por padrão  


