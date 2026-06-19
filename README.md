# Calculadora Científica — C# / .NET

Aplicação de console que interpreta e resolve expressões matemáticas escritas em texto, utilizando **Regex** para parsing, validação e substituição progressiva dos termos da expressão.

---

## Como funciona

O programa lê uma expressão matemática como string e a resolve iterativamente, seguindo as regras de precedência de operadores:

1. Identifica e resolve o **parêntesis mais interno** primeiro
2. Dentro de cada bloco, resolve **multiplicação e divisão** antes de adição e subtração
3. Substitui o resultado parcial na expressão original e repete até restar apenas o valor final

```
Insira uma expressão matemática
(2 + 3) * 4 - 1
19
```

---

## Funcionalidades

- Operações básicas: `+`, `-`, `*`, `/`
- Suporte a **parênteses aninhados**
- Respeito à **ordem de precedência** dos operadores
- Suporte a números decimais com vírgula ou ponto (`1,5` ou `1.5`)
- Tratamento de **números negativos** e simplificação de sinais (`+ -` → `-`)
- Detecção e aviso de **divisão por zero**
- Validação da expressão antes de iniciar o cálculo

---

## Exemplos de uso

| Expressão | Resultado |
|-----------|-----------|
| `2 + 3` | `5` |
| `10 / 2 * 3` | `15` |
| `(2 + 3) * 4` | `20` |
| `(10 - 2) / (2 + 2)` | `2` |
| `3 * -2 + 1` | `-5` |

---

## Tecnologias

- [C#](https://learn.microsoft.com/pt-br/dotnet/csharp/)
- [.NET](https://dotnet.microsoft.com/)
- [System.Text.RegularExpressions](https://learn.microsoft.com/pt-br/dotnet/api/system.text.regularexpressions)

---

## Como executar

**Pré-requisitos:** [.NET SDK](https://dotnet.microsoft.com/download) instalado.

```bash
# Clone o repositório
git clone https://github.com/EduardoVieira778/CalculadoraCientifica.git

# Acesse a pasta do projeto
cd calculadora-cientifica

# Execute
dotnet run
```

---

## Estrutura do código

| Elemento | Responsabilidade |
|----------|-----------------|
| `_patternBasic` | Valida se a expressão contém ao menos uma operação válida |
| `_patternsOps` | Define a precedência: `* /` antes de `+ -` |
| `_patternParenthesis` | Isola o bloco de parênteses mais interno |
| `_patternNegateSum` | Simplifica sinais duplos (`+ -` ou `- +` → `-`) |
| Loop principal | Resolve a expressão progressivamente até o resultado final |

---

## Autor

**Eduardo Vieira**  
[LinkedIn](https://www.linkedin.com/in/eduardo-h-m-vieira) · [GitHub](https://github.com//EduardoVieira778)
