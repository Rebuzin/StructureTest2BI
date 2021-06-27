# Prova Estrutura e Classificação de Dados 2º bimestre


## 1- Métodos de Ordenação  
---

#### **Bubble Sort**
##### O conceito do “Bubble sort” se dá ao fato de que ele mesmo sendo um dos mais simples, percorre o vetor várias vezes fazendo com que o maior elemento flutue para o topo, similar as bolhas em um tanque de água, onde as bolhas procuram seu próprio nível
##### (2, 3, 1) -> (3, 1, 2) -> (1, 2, 3)
##### Ou seja, ele seleciona o número mais alto, levando-o para a ponta direita, assim sucessivamente até formar uma “escada” de forma que pareça flutuar, semelhante a "bolhas"

---

#### **Selection Sort**
##### O conceito do “Selection Sort” se dá ao fato de que ele sempre vai passar o menor/maior valor para a primeira posição “selecionando” o valor
##### (8, 6, 4, 9, 5, 1, 7, 3, 2, 0) ele passa um “sensor” detectando qual é o menor/maior valor, nesse caso faremos como se fosse o menor
##### Primeiro ele vai selecionar o “6”, depois vai selecionar o “4”, então “1” e por fim o “0” e vai mandá-lo para a 1a posição, ficando assim (0, 8, 6, 4, 9, 5, 1, 7, 3, 2)
##### Depois do primeiro processo ele vai passar novamente, selecionando o “8” e assim por diante

---

#### **Insertion Sort**
##### O conceito de “Insertion sort” é similar ao "Bubble Sort", a diferença é que ele “agrupa” os elementos verificados e insere um por vez.
##### (6, 5, 3, 1, 8, 7, 2, 4) ele pré-seleciona o primeiro número, verifica se o segundo é menor que ele e troca.
##### (5, 6, 3, 1, 8, 7, 2, 4) -> (3, 5, 6, 1, 8, 7, 2, 4)-> (1, 3, 5, 6, 8, 7, 2, 4)
##### Assim por diante até formar uma ordem crescente perfeita

---

#### **Quick Sort**
##### O conceito de "Quick sort" se dá a um modelo muito utilizado, além de ser muito interessante, pois rearranja colunas em um gráfico a partir de um modelo “visual”, ele seleciona uma coluna entre outras e as que são menores são movidas para a esquerda, as maiores para a direita, também chamado de divisão e conquista, então ele vai selecionando outras colunas até ficar de forma crescente, similar a uma escada
![Quick Sort BIG Image](https://upload.wikimedia.org/wikipedia/commons/4/4a/Quicksort_example_small.png)

---

### Método mais rápido:
#### Acredito que o método de Ordenação mais rápido seria o Quick Sort, por vez que ele se mostra mais eficaz em grandes sequencias, além de que seu nome traduzido para o português fica "rápido, ágil", porém, acredito que o mais simples seja o Bubble sort, já que ele seleciona número por número, sem ter que rodar processos como o Selection Sort ou sequencias numéricas como o Insertion Sort.

---


## 2- Árvore Binária

---

### Funcionamento

---

#### A árvore binária é uma estrutura não tendo nenhum elemento(árvore vazia) ou com um elemento distinto nomeado como raiz, tendo dois apontamentos para duas estruturas diferentes chamadas sub-árvore esquerda e sub-árvore direita, nela existem nós que vão de zero a dois, sendo um nó de grau zero determinado folha, cada nó pode ter até duas folhas, a profundidade de um nó é determinada pela distância do mesmo até a raiz, e a altura da árvore é denominada pela maior profundidade de um nó

```
Exemplo de Código em JAVA:

public class Arvore {

	public No raiz;

	class No {
		Integer valor;
		No leftSon;
		No rightSon;

		public No (Integer valor) {
			this.valor = valor;
		}
	}
public No inserir(Integer valor) {
	return this.inserir(new No(valor), raiz);

	}

private No inserir (No novo, No anterior) {
	if (raiz == null) {
	raiz = novo;
	return raiz;
}
	if (anterior != null) {
	if (novo.valor <= anterior.valor) {
		anterior.leftSon = this.inserir(novo, anterior.leftSon);
		} else if (novo.valor > anterior.valor) {	
			anterior.rightSon = this.inserir(novo, anterior.rightSon);
		} else {
		return null;
			}
		} else {
		anterior = novo;
		}
		return anterior;
	}
}
```
##### Imagem Exemplo:
![ ](data:image/png;base64,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)

---

#### Já uma árvore balanceada parte do princípio em que ambos os lados tem a mesma altura e as folhas estão no mesmo nível, elas minimizam o número de comparações efetuadas no pior caso para uma busca com chaves de probabilidades de ocorrências idênticas

```
Um exemplo de algoritmo que serve para identificar o desbalanceamento em JAVA:

protected void rebalanceUp(BSTNode<T> node) {
    if (node == null || node.isEmpty()) return;
    rebalance(node);
    if (node.getParent() != null) {
        rebalanceUp(node.getParent());
    }
}

protected int calculateBalance(BSTNode<T> node) {
    if (node == null || node.isEmpty()) return 0;
    return height(node.getRight()) - height(node.getLeft()); 
}

protected void rebalance(BSTNode<T> node) {
    int balanceOfNode = calculateBalance(node);
    
    if (balanceOfNode < -1) {
        if (calculateBalance(node.getLeft()) > 0) {
            leftRotation(node.getLeft());
        }
        rightRotation(node);
    } else if (balanceOfNode > 1) {
        if (calculateBalance(node.getRight()) < 0) {
            rightRotation(node.getRight());
        }
        leftRotation(node);
    }
}
```
##### Imagem Exemplo:
![ ](https://www.inf.ufsc.br/~aldo.vw/estruturas/avl6a.gif)

---

### Diferenças

---

#### A árvore binária balanceada tem uma caracteristica marcante (que também denomina o seu nome) que é estar igualmente distribuida com a mesma distância dos "galhos" até a "raiz" assim como as "folhas" devem estar no mesmo nível(essa informação pode variar dependendo do lugar em que lê) tendo um tempo na ordem de O(log n) para operações de inserção, remoção e pesquisa, sendo sem dúvida, muito bom. Contudo, nas árvores desbalanceadas, o tempo para as devidas operaões é maior, assim como deixa de parecer identado