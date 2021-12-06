# trabalho-aeds1

Trabalho pra disciplina de Algoritmos e Estrutura de Dados 1 - UFV

### Progresso de Funcionalidades

* [ ] Criar uma área de memória interna vazia. Aloca um vetor de células de tamanho N, vamos utilizar alocação dinâmica deste vetor, devido aos altos valores de N que adotaremos.
* [ ] Obter o número de células ocupadas na área de memória. Retorna o número de posições ocupadas no vetor.
* [ ] Inserir um item de dado na área interna de memória, mantendo os itens ordenados.
* [ ] Retirar o primeiro item da área de memória.
* [ ] Retirar o último item da área de memória.
* [ ] Imprimir o conteúdo da área de memória. Somente imprime o conteúdo das células
ocupadas.


### Descrição e Regras de Negócio

A finalidade deste TAD é gerenciar uma área interna de memória de forma que o maior e o menor elemento possam ser removidos com custo constante. A estrutura de dados que deve ser utilizada é uma lista linear duplamente encadeada implementada por cursores. Os cursores são números inteiros que representam posições em um arranjo e são utilizados para simular os apontadores da implementação tradicional das listas lineares duplamente encadeadas. Autilização de cursores evita a alocação e a liberação dinâmica de itens de memória, sendo mais eficiente em aplicações muito dinâmicas em que o número máximo de itens é conhecido.

A retirada de um item de uma lista duplamente encadeada implementada por cursores pode ser realizada a um custo constante, desde que se conheça previamente o endereço do item na lista. Ao manter a lista ordenada, os elementos de menor e ma ior chave estão na primeira e última posição, respectivamente. Os itens de dados (no caso deste trabalho, processos) da lista linear duplamente encadeada implementada por cursores são armazenados em um vetor do tipo Celula. Cada entrada do vetor contém uma estrutura (uma célula) que armazena um item de dado (um processo), um cursor que aponta para o item que sucede aquela entrada (prox) e um cursor que aponta para o item que antecede aquela entrada (ant). No TAD Lista de Processos, além do vetor, são representados dois cursores, primeiro e último, que apontam para o primeiro e o último item da lista, respectivamente. Para facilitar o controle de quando a lista se encontra cheia ou vazia, utilize o campo numCelOcupadas, que indica quantas células da lista estão ocupadas. Os itens armazenados no TAD Lista de Processos precisam ser mantidos ordenados. Você pode utilizar qualquer algoritmo de ordenação que desejar. Para fins de comparação entre os processos, de forma a ordená-los, utilize o PID como chave de ordenação. Isto significa que, na lista, os processos apareceram por ordem de PID. Somente o que foi apresentado até agora não é suficiente para implementar o TAD Lista de Processos. Isto porque, para incluir um novo item de dado na lista, é necessário haver células disponíveis a fim de que a inserção seja realizada. Assim, para gerenciar a lista de células disponíveis em determinado instante, basta incluir um cursor na representação da estrutura de dados (ou seja, na estrutura do próprio TAD Lista de Processos), o qual irá apontar para a primeira célula disponível. Tal cursor foi denominado celulasDisp. As demais células disponíveis podem ser encontradas através do encadeamento entre os cursores das mesmas, isto é, cada célula disponível, possui em seu campo prox o endereço da próxima célula disponível no vetor. A última célula disponível possui o valor -1 no seu campo prox. Da mesma forma, cada célula ocupada possui o endereço da próxima célula ocupada em seu campo prox. A última célula ocupada possui o valor -1 em seu campo prox. O valor -1 também deve ser utilizado no campo ant da primeira célula ocupada e de todas as células disponíveis. Dessa forma, antes de incluir um novo item de dado, remove-se a primeira célula da lista de disponíveis (apontada por celulasDisp) e a insere ordenadamente na lista linear duplamente encadeada que armazena os itens de dados do TAD Lista de Processos. Já ao remover um item de dados, a célula que continha tal item deve ser inserida na lista de disponíveis. Para que a inserção e remoção da lista de disponíveis seja realizada a um custo constante, elas devem ser realizadas na posição apontada por celulasDisp

