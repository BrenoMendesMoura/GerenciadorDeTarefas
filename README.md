# Gerenciador De Tarefas

![image](https://github.com/BrenoMendesMoura/GerenciadorDeTarefas/assets/80074264/5ae3b881-801b-4b37-a1b5-91b139fec0eb)

## Dados da Turma <br>
Dia da semana: Sexta Feira <br>
Período: Noturno <br>

### Integrantes

|RA| NOME COMPLETO| CURSO | TURMA |
| ------------ | ------------ | ------------ | ------------ |
|3021103570|Breno Mendes Moura|TADS|05A|
|3021100282|Victor de souza bernardo|TADS|05A|
|3021104031|Cesar Augusto Martins Vallim|TADS|05A|
|3021103269|Elias Yuri Yoshy Miyashiro|TADS|05A|
|3022201058|Acsa Cristina Sena|TADS|05A|
|3022200274|Matheus souza Martins|TADS|05A|


<hr>

## Explicação do código realizado em c++

### Bibliotecas e typedef struct
Utilizamos 2 bibliotecas para a realização do código, sendo elas:
- `<stdio.h>`, para entrada e saída de mensagens no console.
- `<string.h>`, para manipulação de dados do tipo string.

A utilidade do typedef struct é criar um novo tipo de dados com um nome mais fácil de usar e entender, simplificando a declaração de variáveis da estrutura.

A partir disso declaramos as variáveis globais que utilizamos ao decorrer do código.
```c
#include <stdio.h>
#include <string.h>
#define TAM 10

typedef struct {
  int id;
  char descricao[100];
  int prioridade;
} Tarefa;

Tarefa tarefas[TAM];
int primeiro = 0, ultimo = 0, total = 0;
```


### IsFull e IsEmpty
Essas duas funções são usadas em todo o código, a ideia principal é realizar uma verificação em uma estrutura de condição para determinar se a fila ou pilha está cheia ou vazia.

```c
int isEmpty() {
  return total == 0;
}

int isFull() {
  return total == TAM;
}
```

### Pilha

Copiamos o *pilha* que o professor enviou na segunda-feira e adaptamos ao código, a função da pilha é ordenar como se fosse um empilhamento de acordo com a prioridade da tarefa inserida.
por padrão, sem ordenar com o método bolha, o resultado deveria ser algo nesse estilo:


|id| Tarefa| Prioridade
| ------------ | ------------ | ------------ |
|4|Estudar para AV1|8|
|1|Desenrolar a prova do dia 30-05|9|
|5|Fazer o projeto da faculdade|10|


Observe que o ID não está ordenado, mas a lista de prioridade está em ordem crescente.

```c
void push(Tarefa tarefa) {
  if (isFull()) {
    printf("A pilha de prioridades está cheia.\n");
  } else {
    int i;
    for (i = total - 1; i >= 0; i--) {
      if (tarefa.prioridade > tarefas[i].prioridade) {
        tarefas[i + 1] = tarefas[i];
      } else {
        break;
      }
    }
    tarefas[i + 1] = tarefa;
    total++;
  }
}

Tarefa pop() {
  if (isEmpty()) {
    printf("A pilha de prioridades está vazia.\n");
    Tarefa emptyTask = {0, "", 0};
    return emptyTask;
  } else {
    Tarefa tarefa = tarefas[total - 1];
    total--;
    return tarefa;
  }
}
```
