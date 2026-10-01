Claro — organizei em um `.md` mais **resumido**, incluindo **o que o exercício pede**, as respostas e a ideia principal de cada questão.

 Exercício em Duplas — Preveja Antes de Executar

# Exercício em Duplas — Preveja Antes de Executar

 ## O que o exercício quer?

 O objetivo é **prever o comportamento dos programas antes de executá-los** e observar **quando a linguagem detecta um problema**.

 Para cada trecho, devemos responder:

 1. **Qual será a saída?**
2. **Existe algum problema?**
3. Se existir, ele é detectado:
   - na **compilação**;
   - na **execução**;
   - ou **nunca**?

 O exercício compara como **JavaScript, Python, Go, Java, Rust e C** lidam com tipos, memória, limites e representação de dados.

---

 ## 1\. JavaScript

```
console.log(0.1 * 3 === 0.3);

console.log(9007199254740993);
```

 ### Saída

```
false
9007199254740992
```

 ### Explicação

 - Números de ponto flutuante podem gerar pequenas diferenças de precisão.
- `9007199254740993` ultrapassa o limite de precisão inteira segura do `Number`.

 ### Detecção

 **Nunca.** O programa executa, mas o resultado não corresponde exatamente ao valor matemático esperado.

---

 ## 2\. Python

```
p = "maçã"

print(len(p), len(p.encode()))
```

 ### Saída

```
4 5
```

 ### Explicação

 - `"maçã"` possui 4 caracteres.
- Em UTF-8, esses caracteres ocupam 5 bytes.

 ### Detecção

 **Nunca.** O comportamento é esperado.

---

 ## 3\. Go

```
var b byte = 255

b++

fmt.Println(b)
```

 ### Saída

```
0
```

 ### Explicação

 `byte` é um `uint8`, que possui valores de `0` a `255`.

 Ao incrementar `255`, ocorre overflow:

```
255 + 1 → 0
```

 ### Detecção

 **Nunca.** O overflow de inteiros sem sinal é permitido.

---

 ## 4\. Java

```
int[] v = new int[3];

System.out.println(v[0]);

System.out.println(v[3]);
```

 ### Saída

```
0
```

 Depois ocorre uma exceção:

```
ArrayIndexOutOfBoundsException
```

 ### Explicação

 Um vetor de tamanho 3 possui os índices:

```
0  1  2
```

 `v[0]` é válido e possui valor `0`.

 `v[3]` não existe.

 ### Detecção

 **Na execução.**

 O Java detecta o acesso fora dos limites e lança uma exceção.

---

 ## 5\. Rust

```
let s = String::from("oi");

let t = s;

println!("{} {}", s, t);
```

 ### Saída

 Não existe saída.

 O programa **não compila**.

 ### Explicação

 Rust utiliza o conceito de **ownership (propriedade)**.

 Quando fazemos:

```
let t = s;
```

 a propriedade da `String` é transferida de `s` para `t`.

 Depois da transferência, `s` não pode mais ser utilizado.

 ### Detecção

 **Na compilação.**

 O compilador impede o uso de `s` depois da transferência de propriedade.

---

 ## 6\. C

```
union { int i; float f; } u;

u.f = 1.0f;

printf("%d\n", u.i);
```

 ### Saída

 O valor depende da representação utilizada pela implementação.

 Em uma máquina comum, pode aparecer:

```
1065353216
```

 ### Explicação

 Uma `union` permite que diferentes campos compartilhem a mesma região de memória.

 Primeiro:

```
u.f = 1.0f;
```

 Os bits de `1.0f` são armazenados.

 Depois:

```
u.i
```

 interpreta esses mesmos bits como um `int`.

 Assim, `float` e `int` interpretam a mesma sequência de bits de maneiras diferentes.

 ### Detecção

 Não há necessariamente um erro detectado pelo compilador ou durante a execução; o resultado depende da implementação e da representação dos tipos.

---

 # Resumo geral

 | Nº | Linguagem | Resultado | Problema detectado |
| --- | --- | --- | --- |
| 1 | JavaScript | `false` / `9007199254740992` | Nunca |
| 2 | Python | `4 5` | Nenhum |
| 3 | Go | `0` | Nunca |
| 4 | Java | `0` \+ exceção | Execução |
| 5 | Rust | Não executa | Compilação |
| 6 | C | Depende da implementação | Não necessariamente |

---

 ## O que o exercício demonstra?

 O exercício mostra que **cada linguagem possui mecanismos diferentes para lidar com erros e características dos tipos**.

 - **JavaScript:** permite problemas de precisão numérica sem gerar erro.
- **Python:** diferencia quantidade de caracteres de quantidade de bytes.
- **Go:** permite overflow de inteiros sem sinal.
- **Java:** verifica limites de arrays durante a execução.
- **Rust:** utiliza o sistema de tipos e ownership para detectar problemas durante a compilação.
- **C:** permite manipulação de memória de baixo nível, como `union`, podendo produzir resultados dependentes da implementação.

 ### Principal aprendizado

 O exercício quer mostrar a diferença entre problemas detectados **antes da execução**, problemas detectados **durante a execução** e situações que **não geram erro**, mas podem produzir resultados inesperados.