Atividades Complementares — Autopesquisa

Matrizes associativas

Estruturas que armazenam pares chave–valor, como dict em Python, Map em JavaScript e map em Go. Em Go, a ordem de iteração não é garantida, portanto pode variar.

Registros e tuplas

Estruturas usadas para agrupar diferentes valores. Exemplos: record em Java, struct em Rust e namedtuple em Python.

Listas

Coleções ordenadas de elementos. Python também possui compreensões de lista, uma forma compacta de criar novas listas a partir de outras.

Gerenciamento do monte (heap)

Comparação entre contagem de referências, que libera objetos quando não há mais referências, e marcação e varredura, que identifica objetos ainda alcançáveis e remove os demais.

Verificação e tipagem

Estudo de como as linguagens verificam os tipos, do conceito de tipagem forte e das formas de equivalência de tipos.

Tabela comparativa
Estrutura	Java	Python	Go	Rust
Matriz associativa	Map<K,V> / HashMap<K,V>	dict	map[K]V	HashMap<K,V>
Exemplo	Map<String, Integer> m = new HashMap<>();	m = {"a": 1, "b": 2}	m := map[string]int{"a": 1}	let mut m = HashMap::new();
Mutabilidade	Geralmente mutável	Mutável	Mutável	Mutável com mut
Ordem	HashMap: não garantida	Ordem de inserção	Não garantida	Não garantida
Custo típico	O(1) em média	O(1) em média	O(1) em média	O(1) em média
Registro	record / classe	namedtuple / dataclass	struct	struct
Exemplo	record Pessoa(String nome, int idade) {}	Pessoa = namedtuple("Pessoa", ["nome", "idade"])	type Pessoa struct { Nome string; Idade int }	struct Pessoa { nome: String, idade: u32 }
Mutabilidade	record possui campos finais	namedtuple é imutável	Mutável por padrão	Imutável por padrão; mut permite alteração
Ordem dos campos	Ordem da declaração	Ordem da declaração	Ordem da declaração	Ordem da declaração
Tupla	Não possui tupla nativa geral	(10, "Ana")	Não possui tupla nativa	(10, "Ana")
Mutabilidade da tupla	Depende da implementação	Imutável	—	Pode ser mutável com mut
Acesso à tupla	Depende da implementação	t[0], t[1]	—	t.0, t.1
Acesso típico	Depende da estrutura	Índice: O(1)	—	Índice: O(1)
Conceitos principais
Ordem de iteração dos mapas em Go

A linguagem Go não especifica uma ordem de iteração para map. Por isso, não se deve escrever programas que dependam da ordem em que os elementos aparecem durante um range.

Quando uma ordem específica é necessária, as chaves podem ser copiadas para uma lista, ordenadas e utilizadas para acessar os valores.

Gerenciamento do monte

Existem duas estratégias importantes:

Contagem de referências: cada objeto mantém a quantidade de referências que apontam para ele. Quando essa quantidade chega a zero, o objeto pode ser liberado. Uma limitação é que ciclos de referências podem impedir a liberação automática.

Marcação e varredura (mark-and-sweep): o sistema identifica os objetos que ainda podem ser alcançados a partir das referências válidas. Os objetos que não foram marcados são considerados inacessíveis e podem ser liberados.

Verificação e tipagem

Verificação de tipos: pode ocorrer durante a compilação ou durante a execução.

Tipagem forte: busca impedir operações incompatíveis entre diferentes tipos sem uma conversão apropriada.

Equivalência de tipos: pode ser nominal, quando depende da identidade ou declaração do tipo, ou estrutural, quando depende da estrutura dos tipos.

Conclusão

Os conceitos estudados mostram como diferentes linguagens implementam estruturas semelhantes de maneiras distintas. A comparação entre Java, Python, Go e Rust permite observar diferenças principalmente em sintaxe, mutabilidade, ordenação, custo das operações, gerenciamento de memória e sistema de tipos.
