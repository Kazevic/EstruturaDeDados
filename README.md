# Dados
Dados (e seus vários tipos) são os blocos básicos da programação que representam uma unidade ou um elemento de informação que pode ser acessado via um identificador, como uma variável.

A maioria das linguagens de programação trabalha c/ variações baseadas nestes tipos primitivos:

- INT: Núm. inteiro (-1; 2);

- FLOAT: Núm. decimal (-1,7; 2,8);

- BOOLEAN: Verdadeiro ou falso (true; false);

- TEXT: Sequência ou cadeia de caracteres (#b!c1d; ACC7).

JavaScript (ou JS) usa: number, string, boolean e symbol ("nome simbólico". Cria propriedades únicas em objetos etc.). Já o C# usa: Boolean, Byte, SByte, Int16, UInt16, Int32, UInt32, Int64, UInt64, IntPtr, UIntPtr, Char, Double e Single. O C não tem *Boolean*; *false* é 0, e outros núms. são *true*.

# Estruturas de dados
Normalmente se usam os dados de forma conjunta em computação. A forma como estes dados serão agregados e organizados depende muito de como serão usados e processados, considerando, por exemplo, a eficiência p/ buscas, o volume dos dados trabalhados, a complexidade da implementação e a forma como os dados se relacionam. Estas várias formas de organização são as estruturas de dados.

Cada estrutura de dados tem um conjunto de métodos próprios para fazer operações, como:
- Inserir ou excluir elementos;
- Buscar e localizar elementos;
- Ordenar elementos de acordo c/ alguma ordem especificada.

## Características das estruturas de dados
Elas ṕodem ser:
- lineares (ex. arrays) ou não lineares (ex. grafos);
- homogêneas (todo dado que compõe a estrutura é do mesmo tipo) ou heterogêneas (podem conter dados de vários tipos);
- estáticas (têm tamanho/capacidade de memória fixa) ou dinâmicas (podem expandir).

## Array
O array é a estrutura de dados mais comum e uma lista ordenada de valores:
![image](https://user-images.githubusercontent.com/104698169/212495401-68a850ec-0bb5-4f26-9abe-4be7fd9c238b.png)

No array `listaNumeros`, 4 e 0 sempre serão o primeiro e o último elemento, respectivamente, a menos que seja usada alguma função ou método para mudar a ordem.

Normalmente se trabalha só com um tipo de dado por array; embora o JavaScript aceite declarar arrays de mais de um tipo de dado, por exemplo `["banana", 5, true]`, isso não ocorre na maioria das linguagens de programação.

As linguagens de programação costumam ter criação e manipulação nativa de arrays por ser uma estrutura de dados básica e muitíssimo utilizada. No caso do JavaScript, você pode consultar os métodos e construtores de array no [MDN](https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Reference/Global_Objects/Array).

### Usos
Sendo a mais comum das estruturas, arrays são usados em quase toda situação envolvendo organizar dados dum mesmo tipo, sejam dados recebidos por uma API, enviados a uma base de dados ou até passado via parâmetro para uma função ou método. Eles também podem ser multidimensionais, sendo usados sempre que é preciso tabular dados, e os arrays de 2 dimensões (matrizes) são usados para processar imagens.

## Pilha
Num array, pode-se usar funções próprias para manipular elementos em qualquer posição da lista, mas há casos onde é desejável mais controle sobre as operações que podem ser feitas na estrutura. Aí entra a implementação de estruturas de dados como a pilha (stack) e a fila (queue).

A pilha é uma estrutura de dados que, como o array, é como uma lista. O paradigma principal por trás da pilha é o LIFO (Last In, First Out), que é como numa pilha de livros: o último livro a ser posto é o primeiro a ser retirado.

Assim, só há dois métodos de manipular os dados duma pilha:
- Inserir um elemento no topo da pilha;
- Remover um elemento do topo da pilha.

Diferente dos arrays, as linguagens de programação não costumam ter criação e manipulação nativa de pilhas, mas se pode usar métodos de array para as implementar.

### Usos
Pilhas são mais usadas na pilha de chamadas (*call stack*) dum programa que está sendo executado: a ordem de execução dos processos “chamados” por um programa via funções ou métodos.

Pilhas também são usadas na função "voltar" e "avançar" de navegadores: as URLs visitadas se empilham e, ao chamar a função "voltar", a última URL visitada, isto é, a que está no topo da pilha, é a primeira a ser vista.

## Fila
A fila tem uma estrutura semelhante à pilha, mas com uma diferença conceitual importante: o paradigma por trás da fila é o FIFO (First In, First Out), que é como uma fila de bilheteria: Quem chegou antes será atendido antes de quem chegou depois e ficou atrás na fila.

Assim, também só há duas formas de manipular uma fila:
- Inserir um elemento no final da fila;
- Remover um elemento do início da fila.

### Deque
O deque (double-ended queue) é uma variação da fila que aceita inserir e remover elementos tanto do início como do final da fila, como numa fila num guichê de atendimento: um idoso que chega é atendido antes, isto é, não pode ser posto no fim da fila), assim como quem entrou no final da fila pode desistir de esperar e ir embora (mas não se pode esperar a pessoa avançar na fila para a tirar de lá). Também se pode a entender como uma junção das estruturas de pilha e fila.

### Fila circular
Na fila circular (circular queue), o último elemento é conectado com o primeiro elemento, como num círculo:
A fila circular visa resolver uma limitação da fila linear, que é lidar com espaços vazios que podem se enfileirar após retirar elementos do início da fila.

![image](https://user-images.githubusercontent.com/104698169/212494131-c35ce1fa-8390-49f5-be44-e73663f036f4.png)

### Usos
Um uso fácil de se lembrar para a fila é a fila de impressão dos sistemas operacionais: o último trabalho de impressão a ser adicionado à fila será o último a ser impresso.

Além disso, as requisições feitas a um servidor também são organizadas em fila para serem respondidas, e quando alternamos entre programas usando alt+tab, o sistema operacional gerencia a ordem usando o princípio de lista circular.

## Lista ligada
Há três coisas importantes para sabermos sobre arrays:
1. Na maioria das linguagens de programação, os arrays têm tamanho fixo;
2. Todo elemento ocupa espaços sequenciais na memória;
3. Inserir ou remover elementos do meio do array não é muito simples, pois exige que esses elementos sejam deslocados. Exemplo:
![image](https://user-images.githubusercontent.com/104698169/212495456-dca9d055-32fc-4dba-9412-36b1bd861c16.png)

Este trabalho de deslocamento de elementos é feito internamente pelos métodos nativos de array que as linguagens já têm e que usamos no dia-a-dia, por isso normalmente não nos preocupamos com isso. Mas ele está na implementação do método feita no código-fonte da linguagem.

Como arrays, as listas ligadas também armazenam elementos sequencialmente, mas em vez de armazenar os elementos contíguamente na memória, como nos arrays, as listas ligadas não dependem desse tipo de organização. Elas usam ponteiros para unir os elementos, e cada elemento “aponta” para o endereço de memória do próximo da lista, sem que ele precise estar no bloco de memória seguinte.

Assim, ao trabalhar com listas ligadas também não é preciso deslocar elementos ao incluir ou excluir - considerando que, cada vez que esse deslocamento é feito num array, é preciso reposicionar os elementos em novos espaços de memória. Cada “nó” da lista aponta para o ponteiro de memória onde se encontra o próximo elemento, independente donde esteja este espaço de memória.

![image](https://user-images.githubusercontent.com/104698169/212495633-37eb993b-5f0b-495e-b006-96dbd239448f.png)

### Usos
Lembrando que a lista ligada encadeia elementos apontando para a localização do próximo item na memória, os programas de “álbum de fotos” usam a lista ligada para encadear os arquivos de imagens e “chamar” a próxima imagem/voltar para a imagem anterior via setas do teclado ou botões de “anterior” e “próxima”. O mesmo princípio se aplica para listas de reprodução de música ou vídeo.


## Conjunto
A estrutura de dados conjunto (set) é uma lista não ordenada de elementos únicos, isto é, não se pode repetir o valor dum elemento dentro dum conjunto.

Por exemplo, é perfeitamente possível criar um array com os seguintes elementos:
![image](https://user-images.githubusercontent.com/104698169/212495899-404b962f-b430-4680-9274-865967a1555b.png)

Mas num conjunto, não se pode repetir valores, não importa a ordem dos elementos. A maioria das linguagens de programação mais usadas têm métodos nativos para criar conjuntos. No caso do JavaScript:
![image](https://user-images.githubusercontent.com/104698169/212495949-c0b4ec17-2c5f-4ce3-a863-dad3f4a39abd.png)

### Usos
A estrutura do conjunto vem da matemática, e também se pode fazer operações como união e intersecção em conjuntos de dados. Um dos usos mais comuns desta estrutura é em bancos de dados SQL.

## Dicionário ou hashmap
Dicionário (mapa, map ou hashmap) é uma estrutura que guarda dados em pares de chave e valor e usa estas chaves para achar os elementos associados a elas, diferentemente das estruturas que vimos até agora, que trabalham com listas (sequenciais ou não) só de valores.

Essa descrição parece muito uma outra estrutura que já conhecemos, o objeto. Mas há várias diferenças entre dicionários/mapas e objetos. Por exemplo, pode-se mapear o tamanho dum dicionário (isto é, a quantidade de pares chave/valor) e os dicionários podem aceitar qualquer tipo de dado como chave (objetos só aceitam strings ou symbols). Os dicionários também podem ter performance melhor em buscas e manipulação de dados do que objetos, pois usam referências para as chaves - duma forma similar a ponteiros, as chaves apontam para o endereço de memória de seus valores.

Um aspecto importante sobre dicionários vs objetos: a decisão sobre qual usar dependerá muito da linguagem. Cada linguagem implementa seus próprios métodos para criação de instâncias de objetos ou dicionários e para a manipulação dos dados. Por exemplo, dicionários em Python não eram ordenados por padrão até a versão 3.6, já o objeto Map() em JavaScript é ordenado por padrão; outras linguagens podem suportar dicionários, mas não objetos.

### Usos
O formato `chave:valor` do dicionário é o mais comum para lidar com dados armazenados em bancos de dados, mas não só para isso: o formato é usado sempre que é preciso associar dados e referências para consulta posterior, sejam informações da base de dados de um produto ou até a relação entre o nome dum arquivo e o seu caminho interno na memória do computador, feita pelo sistema operacional.

## Árvore
A árvore é uma estrutura não-sequencial, muito útil para armazenar dados hierarquicamente e que podem ser acessados rapidamente.

Pode-se definir árvore como uma coleção de dados representados por nós e arranjados em níveis hierárquicos (em vez de sequências como as estruturas vistas anteriormente).

Um exemplo de estrutura em árvore são os organogramas de empresas:

![image](https://user-images.githubusercontent.com/104698169/212496594-3556fa0c-d841-49bf-91df-a5e1169363d6.png)

A estrutura mais comum é a árvore binária, que tem no máximo dois nós-filhos a partir do nó inicial (chamado de raiz ou root). Um nó pode ter pais, irmãos e filhos; nós que têm ao menos um filho chamam-se de nós internos, e nós sem filhos chamam-se externos ou folhas:

![image](https://user-images.githubusercontent.com/104698169/212496689-2db3f45c-50bb-441b-a862-aa592d7300b2.png)

A partir da estrutura de árvore binária (com um nó-filho à esquerda e um à direita da raiz) é possível estruturar a chamada BST, ou árvore de busca binária (binary search tree), que usa o princípio do algoritmo de busca binária para estruturar os dados de forma que valores menores estejam à esquerda da raiz e valores maiores à direita. Essa união do algoritmo com a estrutura de dados leva a uma maior eficiência na manipulação de dados, seja para buscar, alterar, incluir ou remover elementos.

## Heap binário
O heap binário é um tipo especial de árvore binária, normalmente usada em computação para implementar filas de prioridade, pois num heap se pode extrair de forma mais eficiente o valor mínimo ou máximo duma lista. Pode-se traduzir heap, muito livremente, como um “monte” ou “porção” de dados.

O heap binário se difere da árvore binária em duas características principais:

- Todos os níveis, exceto o último, têm filhos tanto na esquerda como na direita da raiz. No último nível, os filhos se posicionam o mais à esquerda possível. É o que chamamos de árvore completa.
- Pode ser um heap mínimo (min heap), para extrair o menor valor da árvore, ou heap máximo (max heap) para se extrair o maior valor. Todos os nós devem ser ou ≥ (no caso do heap máximo) ou ≤ (no caso do heap mínimo) do que os valores dos nós-filhos.

### Usos
A estrutura de árvore tem vários usos diversos, como algoritmos de tomada de decisão em aprendizado de máquina, indexação de bancos de dados, indexação e exibição de arquivos e pastas no explorador de arquivos dos sistemas operacionais etc.

O heap binário, como já mencionei, é usado em filas de prioridade (tipo especial de fila onde os elementos são retirados da fila não no padrão FIFO, mas sim organizados por prioridade: mais prioritários no início da fila e menos prioritários no final) e também num algoritmo de ordenação específico, o heap sort.

## Grafo
Outra estrutura não-sequencial, o grafo (graph) é um conjunto de nós (ou vértices), ordenados ou não e ligados por arestas, formando uma estrutura em forma de rede.

![image](https://user-images.githubusercontent.com/104698169/212496740-7ceddabb-ef2b-4d64-ad18-1c5e2e1a7224.png)

O grafo acima pode ser representado da seguinte forma: `V = {1, 2, 3, 4, 5, 6}` (os vértices ou nós) e `E = {(1,2), (2,3), (3,4), (3,6), (4,2), (4,5), (5,1), (5,2), (5,6)}` (as arestas ou edges).

Cada um dos vértices do grafo pode representar um tipo de dado ou sua referência. As arestas podem ser não-direcionadas - como no caso acima, onde as arestas não têm uma direção definida - ou direcionadas, como no caso abaixo:

![image](https://user-images.githubusercontent.com/104698169/212496752-cb825263-3588-48da-b4ce-aa2e243df0ae.png)

As arestas dum grafo também podem ter um valor (também chamado de peso), que representam custo computacional, capacidade etc. para cada “caminho”.

### Usos
As redes sociais usam os grafos para manejar a grande quantidade de dados relacionados entre si que recebem a cada instante. O exemplo mais famoso, a linguagem de consulta GraphQL, foi criada pelo Facebook visando usar grafos para acessar e relacionar dados.

Outro uso famoso para os grafos é o sistema de navegação dos aplicativos de mapas/GPS, que usam grafos e o algoritmo de caminho mínimo (ou shortest path) para traçar rotas.

## Conclusão

Como você pode ter notado, só uma de cada estrutura resumida poderia tomar horas e horas de estudo para entendimento completo do paradigma por trás de cada uma e para implementação de cada classe e método preciso. Várias estruturas já têm métodos e bibliotecas próprios implementados nas diversas linguagens de programação mais usadas, mas é sempre interessante entender o que ocorre “por baixo dos panos”.

O estudo de estruturas de dados, junto com o de algoritmos, é parte essencial dos fundamentos da programação. É interessante combinar o estudo destes temas com a prática “mão na massa” em projetos, para aos poucos agregarmos cada vez mais conhecimento prático e teórico.

Você pode começar aos poucos, estudando a fundo cada uma das estruturas e pesquisando as possíveis implementações na sua linguagem de preferência.
