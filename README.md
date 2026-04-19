# -[ADS]-Introdução-a-Programação


# 🚀 Desafios de Lógica: Do Iniciante ao Junior

Este repositório contém resoluções comentadas para a primeira lista de exercícios de lógica. O objetivo é mostrar a diferença entre um código que **apenas funciona** e um código **profissional (limpo e resiliente)**.

---

## 1. O Informatizador de Nomes
> **Problema:** Criar as iniciais "J.S" a partir de `nome = "João"` e `sobrenome = "Silva"`.

* **Iniciante:** Foca na concatenação simples.
    ```python
    nome = "João"
    sobrenome = "Silva"
    iniciais = nome[0].upper() + "." + sobrenome[0].upper()
    ```
* **Junior:** Usa `f-strings` e protege o código contra espaços em branco acidentais.
    ```python
    # O .strip() evita que um espaço antes do nome quebre a lógica
    iniciais = f"{nome.strip()[0].upper()}.{sobrenome.strip()[0].upper()}"
    ```

---

## 2. O Mestre das Médias
> **Problema:** Calcular a média de `notas = [8.5, 7.0, 9.0, 6.5]` em uma única linha.

* **Iniciante:** Aplica a fórmula matemática básica.
    ```python
    media = sum(notas) / len(notas)
    ```
* **Junior:** Preocupa-se com a segurança (evitar divisão por zero se a lista estiver vazia).
    ```python
    media = sum(notas) / len(notas) if notas else 0
    ```

---

## 3. Inversão Express
> **Problema:** Inverter a string `"Python"` usando fatiamento.

* **Iniciante:** Usa o "truque" do step negativo.
    ```python
    invertida = palavra[::-1]
    ```
* **Junior:** Encapsula em uma função para reutilização e clareza semântica.
    ```python
    def reverse_text(text: str) -> str:
        return text[::-1]
    ```

---

## 4. Analista de E-mail
> **Problema:** Extrair o domínio de `"suporte@empresa.com"` sem loops.

* **Iniciante:** Usa o `.split()` e pega o segundo item da lista.
    ```python
    dominio = contato.split("@")[1]
    ```
* **Junior:** Usa `.partition()`, que é mais seguro caso o separador não exista.
    ```python
    usuario, sep, dominio = contato.partition("@")
    # Se o separador '@' não existir, o domínio não fica vazio por erro de índice
    ```

---

## 5. Ajustador de Preços
> **Problema:** Calcular 15% de desconto em `149.90` e verificar se é menor que `130`.

* **Iniciante:** Faz o cálculo e a comparação separadamente.
    ```python
    preco_final = preco * 0.85
    e_barato = preco_final < 130
    ```
* **Junior:** Usa constantes para facilitar mudanças futuras na regra de negócio.
    ```python
    TAXA_DESCONTO = 0.15
    LIMITE_PROMO = 130
    preco_final = preco * (1 - TAXA_DESCONTO)
    is_affordable = preco_final < LIMITE_PROMO
    ```

---

## 6. Manipulador de Extremos
> **Problema:** Criar uma lista com o menor e o maior valor de `[42, 10, 89, 5, 33]`.

* **Iniciante:** Usa as funções nativas dentro de uma nova lista.
    ```python
    extremos = [min(valores), max(valores)]
    ```
* **Junior:** Valida se a lista possui elementos antes de processar extremos.
    ```python
    extremos = [min(valores), max(valores)] if valores else []
    ```

---

## 7. O Verificador de Paridade (Sem IF)
> **Problema:** Retornar `True` se `27` for par usando apenas matemática.

* **Iniciante:** Usa o operador de resto e comparação.
    ```python
    e_par = (numero % 2 == 0)
    ```
* **Junior:** Utiliza a lógica booleana direta para retorno de funções ou filtros.
    ```python
    # Em performance crítica, poderíamos usar bitwise:
    is_even = not (numero & 1)
    ```

---

## 8. Gerador de Login
> **Problema:** Login com 1ª letra do nome + último sobrenome de `"usuario exemplo silva"`.

* **Iniciante:** Divide a string e concatena os índices.
    ```python
    partes = nome_completo.split()
    login = partes[0][0] + partes[-1]
    ```
* **Junior:** Garante que o login seja sempre em letras minúsculas e sem espaços.
    ```python
    partes = nome_completo.lower().split()
    login = f"{partes[0][0]}{partes[-1]}"
    ```

---

## 9. Expansor de Listas
> **Problema:** Replicar `[1, 2, 3]` 4 vezes.

* **Iniciante:** Usa o operador de repetição.
    ```python
    repetida = base * 4
    ```
* **Junior:** Se os itens da lista fossem objetos (dicionários), usaria *List Comprehension* para evitar erros de referência de memória.
    ```python
    # Garante cópias independentes se houver objetos dentro
    repetida = [item for _ in range(4) for item in base]
    ```

---

## 10. Limpador de Dados
> **Problema:** Limpar `" 12345 "`, converter para `int` e somar `5` em uma linha.

* **Iniciante:** Faz o encadeamento simples (Chaining).
    ```python
    resultado = int(entrada.strip()) + 5
    ```
* **Junior:** Aplica tratamento de erro para inputs que não podem ser convertidos.
    ```python
    try:
        resultado = int(entrada.strip()) + 5
    except ValueError:
        resultado = None # Ou tratamento adequado
    ```

---

**Dica:** O segredo não é decorar comandos, mas entender como os dados fluem!

---
