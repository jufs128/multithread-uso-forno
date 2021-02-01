# Multithread - Uso do Forno
  Os personagens de The Big Bang Theory usam o forno alternadamente, utilizando como base prioridades pré-definidas e quem está na fila ou não.

  As prioridades são: Sheldon/Amy pode usar antes de Howard/Bernadette; Howard/Bernadette pode usar antes de Leonard/Penny; Leonard/Penny pode usar antes de Sheldon/Amy; e, por último, Stuart seguido de Kripke. Se um casal estiver presente, tem preferência. Se mais de um estiver presente, prevalece a prioridade original. Além disso, o casal usa um após o outro.

  Note que pode haver deadlocks quando exatamente um membro de cada casal ou todos os três casais estiverem na fila. Isso é resolvido por Raj, que não utiliza o forno, mas checa se há um deadlock a cada 5 segundos e, nesse caso, escolhe alguém aleatório da fila para ser o próximo da fila.

## Implementação
  O código foi implementado com a biblioteca pthread em C++, sendo cada personagem representado por uma thread e o Raj por uma thread diferente. O forno é protegido por pthread_mutex enquanto é utilizado e o sinal para checar se é o próximo da fila foi feito por pthread_cond.
  
## Entrada
  A única entrada é um inteiro que representa o número de vezes que os personagens vão utlizar o forno. Por exemplo, se a entrada for 2, cada personagem vai entrar na fila para usar o forno duas vezes.
  
## Compilação
  Na pasta code está incluso um Makefile, basta digitar make no prompt de comando da pasta onde se encontra.

## Execução
  A execução deve ser feito na linha de comando, passando o número de vezes em que cada um utilizará o forno. Por exemplo:
  
  *./main 2*
