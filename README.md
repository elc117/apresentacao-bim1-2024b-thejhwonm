# Funções Lambda ou funções anônimas.
As funções lambda têm origem no Cálculo Lambda, uma formalização matemática criada pelo lógico e matemático Alonzo Church na década de 1930. O cálculo lambda foi desenvolvido para explorar a noção de computação e serve como a base teórica para muitos conceitos em programação funcional.

Funções lambda são essencialmente funções sem nome, definidas "inline" no local onde são usadas e possuem uma sintaxe simples.

## Síntaxe Lambda em Haskell.
```Haskell
\parâmetro -> expressão
```
Uma função Lambda que recebe um argumento  **X** e retorna **X + 1**.
```Haskell
(\X -> X + 1)
```

## Lambda em Python.
```Python
lambda x: x + 1
```

# Um exemplo visto em aula, que pode ser encontrado em ["Introdução à programação funcional".](https://liascript.github.io/course/?https://raw.githubusercontent.com/AndreaInfUFSM/elc117-2024b/main/classes/03/README.md#6)

Código em C que remove os hífens de uma string.
```C
#include <stdlib.h>
#include <stdio.h>
#include <string.h>

int main() {
  char *sstr = "a-bra-ca-da-bra";
  char *rstr = malloc(strlen(sstr) + 1);

  int rindex = 0;
  for (int i = 0; i < strlen(sstr); i++) {
    if (sstr[i] != '-') {
      rstr[rindex] = sstr[i];
      rindex++;
    }
  }
  rstr[rindex] = '\0';
  printf("%s\n", rstr);
}
```

Código em Haskell que faz o mesmo.
```Haskell
main = do
  let sstr = "a-bra-ca-da-bra"
  putStrLn (filter (\c -> c /= '-') sstr)
  --putStrLn (filter (/= '-') sstr)
```

# Quando usar ?.
Funções lambda brilham em cenários onde você precisa de uma função curta, de uso único, ou quando utilizar funções de alta ordem como map e filter que  tem como entrada outras funções.

# Quando não usar ?.

Em funções complexas, se a função lambda tiver várias linhas ou uma lógica mais complexa é melhor defini-la como uma função nomeada.

# Alguns exemplos:

```Haskell
filter (\x -> x > 3) [1, 2, 3, 4, 5]  
-- Filtra os números maiores que 3
```


```Haskell
map (\x -> x + 1) [1, 2, 3]
-- Adiciona 1 a cada elemento da lista
```


```Haskell
map (\x -> x * 2) [1, 2, 3]
-- Multiplica cada elemento por 2
```

# Conclusão
Para criar um código legível e ter uma expressão mais clara das operações, principalmente com funções de ordem superior é ideal para a programação funcional em Haskell utilizar funções Lambda. 

# Bibliografias 
[Haskell/Lambdas e operadores](https://pt.wikibooks.org/wiki/Haskell/Lambdas_e_operadores)

[Escrevendo Funções Lambda em Haskell:](https://blog.skill.dev/escrevendo-funcoes-lambda-em-haskell-definicoes-ad-hoc-e-escopo-lexico/)
