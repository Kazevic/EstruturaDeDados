# Dados
Dados são blocos básicos da programação que representam informações acessíveis por um identificador, como uma variável.

A maioria das linguagens de programação usa variações baseadas nestes tipos primitivos:

- INT: Número inteiro (como -1 e 2);

- FLOAT: Número decimal (como -1,7 e 2,8);

- BOOLEAN: Verdadeiro ou falso (true e false);

- TEXT: Sequência de caracteres (como #b!c1d e ACC7).

JavaScript (ou JS) usa: number, string, boolean e symbol (“nome simbólico”. Cria propriedades únicas em objetos etc.). Já o C# usa: Boolean, Byte, SByte, Int16, UInt16, Int32, UInt32, Int64, UInt64, IntPtr, UIntPtr, Char, Double e Single. O C não tem *Boolean*; *false* vira 0, e outros números viram *true*.

# Estruturas de dados
Normalmente, dados são usados juntos em computação, e sua organização depende de como serão processados e usados, considerando, por exemplo, a eficiência para buscas, o volume dos dados trabalhados, a complexidade da implementação e como os dados se relacionam. Estas várias formas de organização são as estruturas de dados.

Cada estrutura de dados tem um conjunto de métodos próprios para fazer operações, como:
- Inserir ou excluir elementos;
- Buscar e localizar elementos;
- Ordenar elementos de acordo com alguma ordem especificada.

## Características das estruturas de dados
Elas podem ser:
- lineares (como arrays) ou não lineares (como grafos);
- homogêneas (todo dado que compõe a estrutura é do mesmo tipo) ou heterogêneas (podem conter dados de vários tipos);
- estáticas (têm tamanho/capacidade de memória fixa) ou dinâmicas (podem expandir).

## Array
O array é a estrutura de dados mais comum e uma lista ordenada de valores:
![image](https://user-images.githubusercontent.com/104698169/212495401-68a850ec-0bb5-4f26-9abe-4be7fd9c238b.png)

No array `listaNumeros`, 4 e 0 sempre serão o primeiro e o último elemento, respectivamente, exceto se for usada alguma função ou método para mudar a ordem.

Normalmente, usa-se só um tipo de dado por array; embora o JavaScript aceite declarar arrays de mais de um tipo de dado, como `["banana", 5, true]`, isso não ocorre na maioria das linguagens de programação.

Linguagens de programação costumam ter suporte nativo para arrays por ser uma estrutura de dados básica e bastante utilizada. No caso do JavaScript, você pode consultar os métodos e construtores de array no [MDN](https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Reference/Global_Objects/Array).

### Usos
Sendo a estrutura mais comum, arrays são usados em quase toda situação para organizar dados do mesmo tipo, sejam dados recebidos por uma API, enviados a um banco de dados ou até passado via parâmetro para uma função ou método. Eles também podem ser multidimensionais, sendo usados sempre na tabulação de dados, e os arrays de 2 dimensões (matrizes) são usados para processar imagens.

## Pilha
Arrays têm funções próprias para manipular elementos em qualquer posição da lista, mas estruturas de dados como pilhas (stacks) e filas (queues) oferecem mais controle sobre as operações realizadas na estrutura.

A pilha é uma estrutura de dados que é como uma lista, como o array. O paradigma principal da pilha é o LIFO (Last In, First Out), semelhante a uma pilha de livros, em que o último a ser colocado é o primeiro a ser retirado.

Logo, só há duas formas de manipular os dados duma pilha:
- Inserir um elemento no topo da pilha;
- Remover um elemento do topo da pilha.

Diferente dos arrays, as linguagens de programação não costumam ter criação e manipulação nativa de pilhas, mas se pode usar métodos de array para as implementar.

### Usos
Pilhas são mais usadas na pilha de chamadas (*call stack*) dum programa em execução, para controlar a ordem de execução dos processos chamados por um programa via funções ou métodos.

As pilhas também são usadas nas funções “voltar” e “avançar” dos navegadores, onde as URLs visitadas são empilhadas, e a última URL visitada, no topo da pilha, é a primeira a ser vista ao chamar a função “voltar”.

## Fila
A fila é semelhante a pilha em sua estrutura, mas com uma diferença conceitual importante: o paradigma da fila é o FIFO (First In, First Out), semelhante a uma fila de bilheteria, onde a pessoa que chega primeiro é atendida primeiro.

Logo, também só há duas formas de manipular uma fila:
- Inserir um elemento no fim da fila;
- Remover um elemento do início da fila.

### Deque
O deque (double-ended queue) é uma variação da fila que permite a inserção e remoção de elementos tanto no início quanto no final da fila, semelhante a uma fila de atendimento, onde idosos ou pessoas com necessidades especiais são atendidas primeiro. Além disso, pode-se entender o deque como uma junção das estruturas de pilha e fila.

### Fila circular
A fila circular (circular queue) conecta o último elemento com o primeiro elemento, formando um círculo. Isso resolve uma limitação da fila linear que lida com espaços vazios após a remoção de elementos do início da fila.

![image](https://user-images.githubusercontent.com/104698169/212494131-c35ce1fa-8390-49f5-be44-e73663f036f4.png)

### Usos
A fila é usada na fila de impressão dos sistemas operacionais, onde o último trabalho adicionado à fila será o último a ser impresso.

Além disso, requisições ao servidor e alternar programas pelo alt+tab usam filas circular e lista circular, respectivamente.

## Lista ligada
Três aspectos importantes dos arrays:
1. Na maioria das linguagens de programação, os arrays têm tamanho fixo;
2. Todo elemento ocupa espaços sequenciais na memória;
3. Inserir ou remover elementos do meio do array é complexo, pois requer o deslocamento desses elementos. Exemplo:
![image](https://user-images.githubusercontent.com/104698169/212495456-dca9d055-32fc-4dba-9412-36b1bd861c16.png)

Os métodos nativos de array fazem o deslocamento interno de elementos e geralmente não precisamos nos preocupar com isso. A implementação é feita no código-fonte da linguagem.

Como arrays, listas ligadas também armazenam elementos sequencialmente, mas em vez de armazenar os elementos contíguamente na memória, elas usam ponteiros para unir os elementos, e cada elemento “aponta” para o endereço de memória do próximo da lista, sem que ele precise estar no bloco de memória seguinte.

Listas ligadas não exigem deslocamento de elementos ao inserir ou remover, ao contrário de arrays, em que é preciso reposicionar os elementos em novos espaços de memória. Cada nó da lista aponta para o ponteiro de memória do próximo elemento, independentemente de onde esteja o espaço de memória.

![image](https://user-images.githubusercontent.com/104698169/212495633-37eb993b-5f0b-495e-b006-96dbd239448f.png)

### Usos
Lembrando que a lista ligada encadeia elementos apontando para a localização do próximo item na memória, os programas de “álbum de fotos” usam a lista ligada para encadear os arquivos de imagens e “chamar” a próxima imagem/voltar para a imagem anterior via setas do teclado ou botões de “anterior” e “próxima”. O mesmo princípio se aplica para listas de reprodução de música ou vídeo.

Programas de álbum de fotos e listas de reprodução de mídia usam a lista ligada para encadear os arquivos e navegar entre eles via setas do teclado ou botões de “anterior” e “próxima”.

## Conjunto
O conjunto (set) é uma lista não ordenada de elementos únicos, ou seja, sem repetição de valores num elemento dum conjunto.

Por exemplo, isto é aceitável num array:

![image](https://user-images.githubusercontent.com/104698169/212495899-404b962f-b430-4680-9274-865967a1555b.png)

Já num conjunto, os valores não podem ser repetidos, independentemente da ordem dos elementos. A maioria das linguagens de programação tem métodos nativos para criar conjuntos. No caso do JavaScript:
![image](https://user-images.githubusercontent.com/104698169/212495949-c0b4ec17-2c5f-4ce3-a863-dad3f4a39abd.png)

### Usos
Conjuntos são baseados em conceitos matemáticos e permitem operações como união e intersecção de dados. Eles são comumente usados em bancos de dados SQL.

## Dicionário ou hashmap
Dicionário (mapa, map ou hasmap) é uma estrutura que armazena dados em pares chave-valor, permitindo acessar os elementos associados a uma chave específica. Ao contrário das estruturas anteriores que trabalham com listas de valores, o dicionário usa chaves para recuperar os valores correspondentes.

Dicionários/mapas são diferentes de objetos. Eles permitem mapear o tamanho (ou seja, a quantidade de pares chave-valor) e aceitam qualquer tipo de dado como chave (objetos só aceitam strings ou symbols). Além disso, podem ter desempenho melhor em buscas e manipulação de dados ao usar referências para as chaves, semelhantes a ponteiros.

A escolha entre dicionários e objetos depende da linguagem de programação utilizada, já que cada uma implementa suas próprias formas de criação e manipulação de dados. Em Python, por exemplo, os dicionários não eram ordenados por padrão até a versão 3.6, enquanto em JavaScript, o objeto Map() é ordenado por padrão. Algumas linguagens podem suportar dicionários, mas não objetos.

### Usos
O formato chave:valor do dicionário é comumente usado para associar dados e referências para consulta posterior, como informações de um produto ou relação entre o nome de um arquivo e seu caminho interno na memória do computador, feito pelo sistema operacional.

## Árvore
Árvores são estruturas não sequenciais e hierárquicas que permitem armazenar e acessar dados de forma eficiente.

Árvore é uma coleção hierárquica de dados representados por nós, em vez de sequências como nas estruturas anteriores.

Os organogramas de empresas usam uma estrutura em árvore:

![image](https://user-images.githubusercontent.com/104698169/212496594-3556fa0c-d841-49bf-91df-a5e1169363d6.png)

A estrutura mais comum é a árvore binária, que tem no máximo dois nós-filhos a partir do nó inicial (chamado de raiz ou root). Nós podem ter pais, irmãos e filhos. Nós com ao menos um filho são internos, e sem filhos são externos/folhas:

![image](https://user-images.githubusercontent.com/104698169/212496689-2db3f45c-50bb-441b-a862-aa592d7300b2.png)

A partir da estrutura de árvore binária (com um nó-filho à esquerda e um à direita da raiz) cria-se a árvore de busca binária (BST ou binary search tree), que usa o algoritmo de busca binária para estruturar os dados para que valores menores estejam à esquerda da raiz e valores maiores à direita. A união do algoritmo com a estrutura de dados aumenta a eficiência na manipulação de dados.

## Heap binário
O heap binário é um tipo especial de árvore binária, normalmente usada em computação para implementar filas de prioridade, pois num heap se pode extrair de forma mais eficiente o valor mínimo ou máximo duma lista. Pode-se traduzir heap, muito livremente, como um “monte” ou “porção” de dados.

O heap (monte ou porção de dados) binário é uma árvore binária especial comumente usada em computação para implementar filas de prioridade, pois heaps podem extrair de forma mais eficiente o valor mínimo ou máximo da lista.

O heap binário difere da árvore binária em duas características principais:

- Todos os níveis, exceto o último, têm filhos tanto na esquerda quanto na direita da raiz. No último nível, os filhos se posicionam o mais à esquerda possível. Isso se chama árvore completa.
- O heap pode ser mínimo (min heap), para extrair o menor valor da árvore, ou máximo (max heap), para extrair o maior valor. Todos os nós devem ser ≥ (com o heap máximo) ou ≤ (com o heap mínimo) aos nós-filhos.

### Usos
A estrutura de árvore tem vários usos diversos, como algoritmos de tomada de decisão em aprendizado de máquina, indexação de bancos de dados e indexação e exibição de arquivos e pastas no explorador de arquivos dos sistemas operacionais.

O heap binário é usado em filas de prioridade e no algoritmo de ordenação heap sort. Filas de prioridade são usadas para organizar elementos por ordem de prioridade (mais prioritários primeiro), enquanto o heap sort é um algoritmo de ordenação que usa a estrutura de heap binário para a ordenação.

## Grafo

Grafo (graph) é uma estrutura em forma de rede composta por nós (ou vértices) ordenados ou não e ligados por arestas.

![image](https://user-images.githubusercontent.com/104698169/212496740-7ceddabb-ef2b-4d64-ad18-1c5e2e1a7224.png)

Forma de representação do grafo acima: `V = {1, 2, 3, 4, 5, 6}` (os vértices ou nós) e `E = {(1,2), (2,3), (3,4), (3,6), (4,2), (4,5), (5,1), (5,2), (5,6)}` (as arestas ou edges).

Cada vértice pode representar um tipo de dado ou sua referência. As arestas podem ser não-direcionadas, como acima, ou direcionadas, como abaixo:

![image](https://user-images.githubusercontent.com/104698169/212496752-cb825263-3588-48da-b4ce-aa2e243df0ae.png)

As arestas dum grafo podem ter um valor (ou peso), que representa custo computacional, capacidade etc. para cada caminho.

### Usos
As redes sociais usam grafos para gerenciar grandes quantidades de dados interconectados. Um exemplo notável é a linguagem de consulta GraphQL, criada pelo Facebook para acessar e relacionar dados usando grafos.

Grafos também são usados no GPS para traçar rotas com algoritmo de caminho mínimo (ou shortest path).

## Conclusão

As estruturas de dados podem ser complexas e podem exigir muito tempo para entendê-las completamente e implementar todos os métodos necessários. Embora muitas dessas estruturas já tenham bibliotecas e métodos implementados, é sempre útil entender o funcionamento interno dessas estruturas.

O estudo de estruturas de dados e algoritmos é essencial na programação. Praticar projetos pode ajudar a agregar conhecimento prático e teórico.

Você pode começar aos poucos, estudando a fundo cada estrutura e suas implementações na sua linguagem preferida.
