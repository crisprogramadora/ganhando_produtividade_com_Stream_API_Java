# ganhando_produtividade_com_Stream_API_Java
Bootcamp Java Cloud Native - Bradesco

# Stream API

Stream, trata-se de uma solução poderosa para selecionar coleções de maneira declarativa, ao invés da tradicional e burocrática de forma imperativa.

Categorias principais das operações na API Stream:

* Operações Intermediárias: são aquelas que retornam uma nova Stream e permitem encadear diversas operações, formando um pipeline de processamento de dados. São elas:
  
filter(Predicate<T> predicate): Filtra os elementos da Stream com base em um predicado. Retorna uma nova Stream contendo apenas os elementos que atendem às categorias do predicado. Exemplo: stream.filter(n -> n > 5).

map(Function<T, R> mapper): Transforma cada elemento do Stream usando uma função especificada e retorna um novo Stream contendo os elementos resultantes. Exemplo:stream.map(s -> s.toUpperCase()).

sorted(): Classifica os elementos do Stream em ordem natural (se os elementos são comparáveis) ou de acordo com um comparador fornecido. Exemplo:stream.sorted().

distinct(): Remove elementos duplicados do Stream, considerando a implementação do método equals() para comparação. Exemplo:stream.distinct().

limit(long maxSize): Limite o número de elementos do Stream aos maxSize primeiros elementos Exemplo: stream.limit(10).

skip(long n): Pula os primeiros n elementos do Stream e retorna um novo Stream sem eles. Exemplo:stream.skip(5).

* Operações Terminais: são aquelas que encerram o pipeline e produzem um resultado final. São elas:
* 
forEach(Consumer<T> action): Executa uma ação para cada elemento do Stream. Exemplo:stream.forEach(System.out::println).

toArray(): Converte um Stream em um array contendo os elementos do Stream. Exemplo:stream.toArray().

collect(Collector<T, A, R> collector): Coleta os elementos do Stream em uma estrutura de dados específica, como uma lista ou um mapa. Exemplo: stream.collect(Collectors.toList()).

count(): Retorna o número de elementos no Stream. Exemplo:stream.count().

anyMatch(Predicate<T> predicate): Verifique se algum elemento do Stream atende ao predicado especificado. Exemplo:stream.anyMatch(s -> s.startsWith("A")).

allMatch(Predicate<T> predicate): Verifique se todos os elementos do Stream atendem ao predicado especificado. Exemplo:stream.allMatch(n -> n > 0).

noneMatch(Predicate<T> predicate): Verifique se nenhum elemento do Stream atende ao predicado especificado. Exemplo: stream.noneMatch(s -> s.isEmpty()).

min(Comparator<T> comparator)e max(Comparator<T> comparator): Encontra o elemento mínimo e máximo da Stream, respectivamente, de acordo com o comparador fornecido. Exemplo: stream.min(Comparator.naturalOrder())oustream.max(Comparator.naturalOrder()).

reduce(T identity, BinaryOperator<T> accumulator): Combina os elementos do Stream usando o acumulador especificado e retorna o resultado final. Exemplo:stream.reduce(0, (a, b) -> a + b).

# Lambda

As expressões lambda permitem representar interfaces funcionais (interfaces com um único método abstrato) de forma mais concisa e possibilitam escrever código no estilo funcional.
As interfaces funcionais desempenham um papel crucial na programação funcional em Java, pois servem de base para o uso de expressões lambda.
Uma função lambda é uma função sem declaração, isto é, não é necessário colocar um nome, um tipo de retorno e o modificador de acesso. A ideia é que o método seja declarado no mesmo lugar em que será usado.
As funções lambda em Java têm a sintaxe definida como (argumento) -> (corpo).

# Referência de método

Method Reference é um novo recurso do Java 8 que permite fazer referência a um método ou construtor de uma classe (de forma funcional) e assim indicar que ele deve ser utilizado num ponto específico do código, deixando-o mais simples e legível.
Para utilizá-lo, basta informar uma classe ou referência seguida do símbolo “::” e o nome do método sem os parênteses no final.

# Functional Interface

Qualquer interface com um SAM (Single Abstract Method) é uma interface funcional e sua implementação pode ser tratada como expressões lambda. Algumas functional interfaces são:

Consumer<T>: Representa uma operação que aceita um argumento do tipo T e não retorna nenhum resultado. É utilizada principalmente para realizar ações ou efeitos colaterais nos elementos do Stream sem modificar ou retornar um valor. Ex: Imprimir números pares de uma lista.

Supplier<T>: Representa uma operação que não aceita nenhum argumento e retorna um resultado do tipo T. É comumente usada para criar ou fornecer novos objetos de um determinado tipo. Ex: Usar o Supplier com expressão lambda para fornecer uma saudação personalizada e obter uma lista com 5 saudações.

Function<T, R>: Representa uma função que aceita um argumento do tipo T e retorna um resultado do tipo R. É utilizada para transformar ou mapear os elementos do Stream em outros valores ou tipos. Ex: Usar a função para dobrar todos os números no Stream e armazená-los em outra lista.

Predicate<T>: Representa uma função que aceita um argumento do tipo T e retorna um valor booleano (verdadeiro ou falso). É comumente usada para filtrar os elementos do Stream com base em alguma condição. Ex: Usar o predicate para filtrar números pares no Stream e armazená-los em outra lista.

BinaryOperator<T>: Representa uma operação que combina dois argumentos do tipo T e retorna um resultado do mesmo tipo T. É usada para realizar operações de redução em pares de elementos, como somar números ou combinar objetos. Ex: Usar o BinaryOperator para somar todos os números no Stream.


Referências
[1] "Exemplos de API de coleções Java - cami-la." Github. Disponível em: https://github.com/cami-la/collections-java-api-2023 .


Sobre
Este repositório contém um resumo do curso "Ganhando Produtividade com Stream API Java". O curso foi projetado para ajudar desenvolvedores Java a aproveitar ao máximo o poderoso API Stream introduzido no Java 8.
