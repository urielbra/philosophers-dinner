# Philosopher Dinner
### Lab. Sistema Operacionais
### Guilherme Giacomin & Uriel Braga

#### How to execute

`$ gcc "file_name".c -lpthread`
`$ ./a.out`

#### Exaplanation (in portuguese):


O Jantar dos filósofos foi proposto por Dijkstra em 1965 como um problema de sincronização. A partir de então todos os algoritmos propostos como soluções de sincronização acabaram sendo relacionados ou testados contra o problema do Jantar dos filósofos.

Cinco filósofos estão sentados em uma mesa redonda para jantar. Cada filósofo tem um prato com espaguete à sua frente. Cada prato possui um garfo para pegar o espaguete. O espaguete está muito escorregadio e, para que um filósofo consiga comer, será necessário utilizar dois garfos. 

Lembre-se que é apenas uma analogia. Nesse sentido, cada filósofo alterna entre duas tarefas: comer ou pensar. Quando um filósofo fica com fome, ele tenta pegar os garfos à sua esquerda e à sua direita; um de cada vez, independente da ordem. Caso ele consiga pegar dois garfos, ele come durante um determinado tempo e depois recoloca os garfos na mesa. Em seguida ele volta a pensar.

*** Por definição, o problema em questão é: ***

Você é capaz de propor um algoritmo que implemente cada filósofo de modo que ele execute as tarefas de comer e pensar sem nunca ficar travado?

Esta é a parte na qual relacionamos o problema com o conteúdo de Sistemas Operacionais, no caso, o travamento dos filósofos seria análogo ao DEADLOCK.

##### Solução 1 - Eliminar a Posse e Espera

Nesta solução, quando um filósofo pega o palito à esquerda ele tenta pegar o da direita, avalia se foi possível e se sim, come. Se não, solta o palito da mão esquerda e espera um tempo aleatório, depois, por estar em um loop, tenta novamente. Essa solução resolve o DeadLock


##### Solução 2 - Ataque a ordem de espera circular

Esta solução alternativa tem uma abordagem diferente: é definido que, se o filósofo estiver em uma cadeira ímpar, ele pega o palito da direita primeiro e, se o filósofo estiver em uma cadeira par, pega o palito da esquerda primeiro. Isso faz com que não ocorra *deadlock*.
