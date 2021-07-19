# :back: [Processos](../../../README.md#low-level-programming)

## Tabela padrão
A tabela de padrão de processos do terminal Unix é mostrada ao passar o comando [ps](#ps):

| PID | TTY | TIME | CMD |
| :-: | :-: | :-: | :- |
| 16617 | pts/1 | 0:00:00 | bash |
| 21296 | pts/1 | 0:00:00 | ps |

<br>

## Estados de um processo
Um processo pode estar em:
* **execução**
* **background**
* **suspenso**

> Todos os processos encontram-se numa lista chamada **jobs**.

<br>

## Comandos relacionados à processos
| Processos | Descrição |
| :---: | :--- |
| <a name="ps">[ps](terminalCheatSheet.md#ps)</a> | motra uma lista de processos sendo executados no momento |
| `pstree` |  |
| `top` |  |
| `sleep` | roda um processo que para o terminal durante um determinado tempo |
| `sleep 8` | para o terminal durante 8 segundos |
| `sleep 8 &` | roda o processo no background durante 8 segundos  |
| `[ctrl]+[z]` | suspende um processo ativo |
| `[ctrl]+[c]` | mata um processo |
| `bg` | retoma o último processo |
| `bg` | retoma o último processo |
| `fg` | retoma um processo suspenso da lista de jobs |
| `fg %1` | retoma o processo da posição [1] |
| `jobs` | mostra a lista de todos os processos |
| `kill` | mata um processo |
| `kill %1` | mata o processo na posição [1] da lista de processos |
| `kill 22462` | mata o processo com PYD 22462 |
| `kill -9 22462` | mata de forma abrupta (à força) o processo com PYD 22462 |


