# Exercício em Duplas aula 006

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
