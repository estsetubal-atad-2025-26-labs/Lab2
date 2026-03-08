# ATAD 2025/26

## Lab 2 - Linguagem C | Tipos de Dados e Documentação Doxygen

🎯  **Objetivos**:

- Sistematizar utilização de repositórios GitHub e ambiente de programação;

- Compreender sintaxe da Linguagem C, mecanismos de entrada/saída, tipos de dados e modularidade;

- Domínio dos tipos de dados primitivos, compostos e arrays;

- Produção (assistida) de documentação *Doxygen*.

> [!IMPORTANT]
> Utilize o *template* `CProgram_Template` disponível no *GitHub* para cada um dos exercícios propostos:
>
> <https://github.com/estsetubal-atad/CProgram_Template>
>
> **How-To Repositórios**: <https://www.youtube.com/watch?v=THsizwp30r0>

---

### 1 | 🟰 Programa `QuadraticFormula`

$$
x = \frac{-b \pm \sqrt{b^2 - 4ac}}{2a}
$$

Pretende-se um programa que calcule as raízes de uma equação quadrática (através da fórmula resolvente), exemplificando-se a interação pretendida com o utilizador:

```console
---  QUADRATIC EQUATION SOLVER a^2 + bx + c = 0 ---

a?: 1
b?: 2
c?: -15

x = {3.00, -5.00}
```

1. Crie um projeto na pasta `QuadraticFormula` a partir do *template* indicado no início da ficha;

2. Identifique e produza o código necessário para o programa se comportar como indicado, com as seguintes salvaguardas:

    - coloque todo o código na função `main`;

    - `a`, `b` e `c` têm de ser valores inteiros válidos, solicitados ao utilizador. Consulte o `README` do `CProgramTemplate` para verificar como pode fazê-lo, utilizando o *módulo* `input`;    

    - se o corpo da raiz quadrada na fórmula resolvente for *negativo*, significa que a equação não tem solução. Se for o caso, indique isto ao utilizador.

    - as raízes obtidas não serão necessariamente valores inteiros; apresente as raízes com 2 casas decimais.

    - é necessária a inclusão do módulo `<math.h>` para utilização da função `sqrt` para cálculo de raízes quadradas, acompanhada da *flag* `-lm` para compilação do programa;

3. Compile e teste o seu programa, testando várias equações. Pode confirmar os seus resultados em: <https://www.matematica.pt/util/calculadora-equacao-2-grau.php>.


### 2 | 📶 Programa `Arrays`

Pretende-se um programa *modular* que faça algumas travessias, manipulações e verificações em arrays.

Exemplo de execução do programa:

```console
--- Arrays ---

[1, 4, 7, 10, 14, 15]
Detected sorting = increasing

[15, 14, 10, 7, 4, 1]
Detected sorting = decreasing

[15, 7, 10, 14, 4, 1]
Detected sorting = none
```

1. Crie um (novo) projeto na pasta `Arrays` a partir do *template* indicado no início da ficha;

2. Crie um **módulo** `arrays` com os respetivos ficheiros `.h` e `.c`;

3. Declare no *header file* as seguintes funções:

   - `void arrayPrint(int arr[], int arrLength)` - imprime um array na consola (preferencialmente no formato exemplificado acima);
   - `void arrayReverse(int arr[], int arrLength)` - inverte a ordem dos elementos de um array;
   - `int arrayIsSorted(int arr[], int arrLength)` - que retorna:
      - `1` se o array estiver ordenado de forma crescente;
      - `-1` se estiver ordenado de forma decrescente;
      - `0` se não estiver ordenado.

4. :robot: Peça ao ChatGPT (ou LLM similar) para "gerar a documentação *doxygen*" destas funções e adicione-as ao ficheiro. **Estude a sua sintaxe**.

5. No *source file* do módulo implemente as funções anteriores - preferencialmente, sem recurso a LLM :x::robot:, mas se utilizar faça uso das [boas práticas](../../../BoasPraticas-LLM).

6. No `main` declare **um** (!) array de inteiros e replique o *output* do programa exemplificado acima.

   - :bulb: Na última configuração do array, foram *trocados* (manualmente) os elementos nos índices `1` e `3`.

   - :bulb: Note que, durante a codificação, consegue visualizar a documentação *doxygen* das funções declaradas.

7. Gere a documentação *doxygen*, utilizando o comando `doxygen` (consulte o `README.md`, se necessário).

### 3 | 💰 Programa Gestão de Despesas Mensais

Escreva um programa modular em C para gerir despesas mensais. O programa deverá definir um tipo composto `Expense` e funções para manipular despesas num módulo separado.

#### Requisitos

1. **Definir o tipo `Expense`**  
   - Deve representar uma despesa mensal e conter:  
     - **Descrição** (*string* de até 50 caracteres).  
     - **Valor** (float).  

2. **Criar um módulo (`expenses.h` e `expenses.c`)** com as seguintes funções (e correspondente documentação *doxygen*):  

   - `Expense expenseCreate(const char *description, float value);`  
     - Cria e retorna uma nova despesa.  
   - `void expensePrint(Expense e);`  
     - Exibe a despesa no formato:  
       ```
       Despesa[Descrição: Renda, Valor: 500.00€]
       ```
   - `float expensesTotal(Expense arr[], int length);`  
     - Retorna a soma das despesas num array.

3. **No programa principal (`main.c`)**:  
   - Criar 3 despesas.  
   - Mostrar as despesas criadas.  
   - Calcular e exibir o valor total das despesas.  

---

> [!IMPORTANT]
> Termine os exercícios em casa.

---

@ bruno.silva@estsetubal.ips.pt

