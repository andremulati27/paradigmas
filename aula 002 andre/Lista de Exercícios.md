### 1. Genealogia das linguagens

A evolução das linguagens não é uma escada em que uma linguagem simplesmente substitui a anterior. Diferentes linguagens continuam úteis para diferentes problemas.

Dois fatores históricos são:

* **Necessidades diferentes:** uma linguagem criada para negócios pode continuar sendo usada mesmo após o surgimento de linguagens mais modernas.
* **Compatibilidade e legado:** programas, ferramentas e profissionais já existentes dificultam a substituição completa de uma linguagem.

### 2. Short Code, Speedcoding e A-0/A-1/A-2

* **Short Code:** buscava facilitar a programação de computadores, usando códigos mais próximos de expressões matemáticas.
* **Speedcoding:** facilitava a programação no IBM 701 por meio de uma linguagem simbólica e de um sistema que traduzia os comandos.
* **A-0/A-1/A-2:** buscavam automatizar a programação, permitindo escrever operações de forma mais abstrata.

Chamá-los simplesmente de **compiladores modernos** é impreciso porque eram sistemas pioneiros, com recursos e objetivos bem mais limitados que os compiladores atuais.

### 3. Lisp e Fortran

**Fortran** surgiu principalmente para computação científica e matemática. Trabalhava com dados numéricos e favorecia cálculos e algoritmos numéricos.

**Lisp** surgiu ligado à inteligência artificial. Sua principal característica era a representação de dados por **listas e expressões simbólicas**, favorecendo processamento simbólico e programação recursiva.

### 4. Contribuições do ALGOL 60

Três contribuições importantes foram:

* introdução/fortalecimento da **estrutura de blocos**;
* uso de **recursão**;
* influência no projeto de várias linguagens posteriores, especialmente na sintaxe e estrutura de programas.

Uma linguagem pode ser muito influente sem dominar o mercado porque **influência técnica e sucesso comercial são coisas diferentes**. O ALGOL 60 influenciou pesquisadores e projetistas, mas não teve a mesma adoção comercial de linguagens como Fortran ou COBOL.

### 5. COBOL

COBOL foi projetada para **processamento comercial**, portanto priorizava facilidade de leitura por profissionais de negócios e programadores.

Sua sintaxe utilizava palavras próximas do **inglês**, tornando os programas mais legíveis. Também possuía estruturas de **registros**, adequadas a dados comerciais, como clientes e funcionários.

COBOL recebeu forte influência do **FLOW-MATIC**, especialmente na preocupação com uma linguagem voltada para aplicações comerciais e com maior facilidade de leitura.

### 6. ALGOL → Pascal → C e Prolog

Uma cadeia de influência pode ser representada assim:

**ALGOL → Pascal → C**

* **ALGOL:** influenciou a estrutura de blocos e a sintaxe de linguagens posteriores.
* **Pascal:** aproveitou conceitos estruturados do ALGOL e enfatizou programação estruturada e tipos.
* **C:** recebeu influência de linguagens anteriores, incluindo ALGOL e Pascal, combinando programação estruturada com acesso de baixo nível.

Essa linhagem é predominantemente **imperativa**, pois descreve como o computador deve executar operações.

Já **Prolog** segue uma proposta **declarativa**: o programador descreve fatos e regras, e o sistema busca as soluções.

### 7. Ada

Ada foi desenvolvida para sistemas de grande escala e críticos, nos quais **confiabilidade e segurança** são fundamentais.

* **Tipos fortes:** ajudam a detectar erros.
* **Pacotes:** permitem organizar e encapsular componentes.
* **Concorrência:** permite trabalhar com várias atividades simultâneas.
* **Confiabilidade:** reduz a possibilidade de erros em sistemas complexos.

Essas características são especialmente importantes em áreas como sistemas militares, aeronáuticos e de controle.

### 8. Java e a Web

Java não foi criada originalmente para a Web. Ela surgiu inicialmente com objetivos relacionados a dispositivos e sistemas embarcados.

Com a expansão da **Web**, suas características — como portabilidade e execução em diferentes plataformas — tornaram-se muito atraentes. Assim, uma mudança no contexto tecnológico pode fazer uma linguagem criada para determinado objetivo encontrar **um novo domínio de aplicação**.

### 9. C# e Java/C++

Duas decisões importantes de C# são:

* **Coleta automática de lixo:** assim como Java, C# automatiza o gerenciamento de memória, reduzindo erros comuns de alocação e liberação manual encontrados em C++.
* **Propriedades:** C# oferece uma forma mais simples e controlada de acessar atributos de objetos, evitando a necessidade de escrever muitos métodos `get` e `set` manualmente.

Assim, C# combina ideias de Java e C++, procurando oferecer **produtividade, segurança e integração com o ambiente .NET**.

### 10. Linha do tempo — oito linguagens e quatro paradigmas

| Período | Linguagem    | Paradigma              | Influência                                                 |
| ------- | ------------ | ---------------------- | ---------------------------------------------------------- |
| 1957    | **Fortran**  | Imperativo             | Influenciou linguagens científicas posteriores             |
| 1958    | **Lisp**     | Funcional              | Originou uma importante linhagem de linguagens funcionais  |
| 1959    | **COBOL**    | Imperativo             | Influenciou linguagens voltadas a negócios                 |
| 1960    | **ALGOL 60** | Imperativo             | Influenciou fortemente a estrutura de Pascal e C           |
| 1970    | **Pascal**   | Imperativo/estruturado | Influenciou linguagens de ensino e programação estruturada |
| 1972    | **C**        | Imperativo             | Influenciou C++, Java e C#                                 |
| 1972    | **Prolog**   | Lógico/declarativo     | Desenvolveu uma linhagem baseada em lógica                 |
| 1995    | **Java**     | Orientado a objetos    | Influenciou linguagens modernas, incluindo C#              |

Assim, a linha não representa apenas uma sequência temporal: **ALGOL influenciou Pascal e C; C influenciou Java e C#; Lisp representa uma linhagem funcional; Prolog representa a programação lógica; e COBOL/Fortran representam caminhos especializados em negócios e computação científica.**
