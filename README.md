# Gerenciador De Tarefas

<style>
  
.centered {
    text-align: center;
}
  
</style>

<div class="centered">
  
![image](https://github.com/BrenoMendesMoura/GerenciadorDeTarefas/assets/80074264/5ae3b881-801b-4b37-a1b5-91b139fec0eb)
  
</div>



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

```c
#include <stdio.h>
#include <string.h>
#define TAM 10

typedef struct {
  int id;
  char descricao[100];
  int prioridade;
} Tarefa;
```
