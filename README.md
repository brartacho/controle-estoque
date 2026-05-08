# Controle de Estoque

Atividade prática do curso de Arquitetura de Sistemas. Sistema de cadastro e comparação de produtos em estoque via linha de comando, desenvolvido em Java com foco em orientação a objetos.

## Funcionalidades

- Cadastro de produtos com nome, categoria, preço e quantidade
- Exibição do resumo de cada produto com status do estoque
- Comparação de quantidade e valor total em estoque entre os produtos

## Categorias de Produto

| Categoria | Variável |
|-----------|----------|
| Comida | `comida1` |
| Limpeza | `produtoLimpeza1` |
| Higiene | `produtoHigienePessoal1` |

## Status do Estoque

| Quantidade | Status |
|------------|--------|
| 0 | Sem estoque |
| 1 – 5 | Estoque baixo |
| 6 – 20 | Estoque normal |
| > 20 | Estoque alto |

## Estrutura do Projeto

```
controle-estoque/
├── Produto.java           # Classe de domínio com atributos e regras do produto
└── ControleEstoque.java   # Classe principal com leitura de dados e comparações
```

### `Produto.java`

Representa um produto no estoque. Responsabilidades:

- Armazenar nome, categoria, preço e quantidade
- Validar quantidade mínima (não permite valores negativos)
- Calcular valor total em estoque (`preço × quantidade`)
- Informar disponibilidade e status do estoque
- Exibir resumo formatado

### `ControleEstoque.java`

Classe principal com o fluxo da aplicação. Responsabilidades:

- Ler e validar entradas do usuário (texto, inteiro, decimal)
- Cadastrar os três produtos via terminal
- Exibir o resumo de cada produto
- Comparar os produtos dois a dois (quantidade e valor total)

## Como Executar

**Pré-requisito:** JDK 11 ou superior instalado.

```bash
# Compilar
javac Produto.java ControleEstoque.java

# Executar
java ControleEstoque
```

## Exemplo de Uso

```
=== Cadastro: Comida ===
Nome do produto (campo obrigatório): Arroz
O preço do produto (ex: 25.50 ou 25,50): R$ 8,90
Quantidade em estoque (ex: número inteiro >=0): 15

=== Resumo dos Produtos Cadastrados ===
Produto 1 - Comida:
Categoria: Comida
Produto: Arroz
Preço: R$ 8,90
Quantidade: 15
Disponível: Sim
Status do estoque: Estoque normal
Valor total em estoque: R$ 133,50

=== Comparação Final ===
--- Comparação de Quantidade em Estoque
...
--- Comparação de Valor Total em Estoque
...
```

## Conceitos Aplicados

- Encapsulamento com atributos `private` e getters/setters
- Separação de responsabilidades entre classes
- Validação de entrada com tratamento de exceções (`NumberFormatException`)
- Formatação de saída com `printf`
- Métodos de negócio coesos e reutilizáveis
