# Computação Quântica com Qiskit - Curso Intensivo do Prof. Nathan Lima

> Coleção de notebooks desenvolvidos para estudo e experimentação dos principais fundamentos da Computação Quântica utilizando **Qiskit**, com ênfase na compreensão matemática dos fenômenos quânticos, construção de circuitos, simulação de algoritmos e interpretação física dos resultados.

## Sobre o projeto

Este repositório reúne três notebooks produzidos durante estudos introdutórios em Computação Quântica utilizando o ecossistema **IBM Qiskit**.

Ao invés de simplesmente executar códigos, o objetivo deste material é construir uma compreensão gradual dos conceitos fundamentais da computação quântica, relacionando teoria matemática, representação física e implementação computacional.

Todos os experimentos foram desenvolvidos em ambiente **Google Colab**, utilizando o simulador **Qiskit Aer**, permitindo observar exatamente a evolução dos estados quânticos antes da medição.

# Objetivos

Os notebooks procuram desenvolver os seguintes conceitos:

- Compreensão da representação matemática de qubits;
- Construção de circuitos quânticos utilizando Qiskit;
- Estudo das principais portas quânticas;
- Interpretação da evolução dos vetores de estado;
- Visualização geométrica na Esfera de Bloch;
- Criação de estados emaranhados;
- Análise estatística das medições quânticas;
- Introdução aos protocolos básicos de comunicação quântica.

Mais do que apresentar comandos da biblioteca, o foco está em compreender **por que** cada operação produz determinado comportamento físico e matemático.

# Tecnologias utilizadas

- Python 3
- Qiskit
- Qiskit Aer
- Qiskit IBM Runtime
- NumPy
- Matplotlib
- Google Colab


# Conteúdos abordados

## 1. Introdução ao modelo de computação quântica

O projeto inicia apresentando a diferença entre computação clássica e computação quântica.

Enquanto um bit clássico assume apenas os estados

\[
0 \quad \text{ou} \quad 1,
\]

um qubit pode existir em uma combinação linear destes estados, denominada **superposição**:

\[
|\psi\rangle=\alpha|0\rangle+\beta|1\rangle,
\]

onde

\[
|\alpha|^2+|\beta|^2=1.
\]

Essa restrição garante que a soma das probabilidades de medição seja igual a 1.

Os notebooks exploram esse conceito tanto matematicamente quanto por meio de simulações.

---

# 2. Construção de circuitos quânticos

Os experimentos utilizam a classe

```python
QuantumCircuit
```

para modelar circuitos compostos por:

- qubits;
- bits clássicos;
- portas lógicas;
- medições.

Cada circuito representa uma sequência ordenada de transformações unitárias aplicadas ao vetor de estado.

Durante os experimentos são utilizados simuladores para acompanhar cada etapa da evolução do sistema antes da medição.

---

# 3. Porta Hadamard

Um dos principais tópicos estudados é a porta **Hadamard**, responsável por criar estados de superposição.

Sua representação matricial é

\[
H=
\frac1{\sqrt2}
\begin{bmatrix}
1&1\\
1&-1
\end{bmatrix}.
\]

Nos notebooks são analisadas as transformações

\[
H|0\rangle=
\frac{|0\rangle+|1\rangle}{\sqrt2},
\]

e

\[
H|1\rangle=
\frac{|0\rangle-|1\rangle}{\sqrt2}.
\]

Além disso, demonstra-se experimentalmente que

\[
H^2=I,
\]

mostrando que a aplicação sucessiva da porta Hadamard restaura o estado inicial.

---

# 4. Esfera de Bloch

Um notebook é dedicado exclusivamente à interpretação geométrica dos estados de um único qubit.

A Esfera de Bloch fornece uma representação tridimensional onde:

- polo norte representa o estado \(|0\rangle\);
- polo sul representa o estado \(|1\rangle\);
- pontos sobre o equador representam diferentes superposições.

Essa visualização permite compreender intuitivamente como portas quânticas realizam rotações no espaço de estados.

Foram utilizados recursos do Qiskit para visualizar dinamicamente essas transformações.

---

# 5. Vetor de estado

Ao invés de observar apenas os resultados das medições, os notebooks utilizam

```python
Statevector
```

para obter o vetor de estado exato produzido por cada circuito.

Essa abordagem permite verificar diretamente:

- amplitudes complexas;
- normalização do estado;
- efeitos das portas unitárias;
- evolução do sistema antes do colapso da função de onda.

Essa técnica aproxima o estudo computacional da formulação matemática da Mecânica Quântica.

---

# 6. Simulação quântica

Os experimentos utilizam

```python
AerSimulator
```

para executar circuitos em ambiente clássico.

O simulador permite:

- executar milhares de medições;
- estimar distribuições de probabilidade;
- comparar teoria e resultados experimentais;
- validar o comportamento esperado dos algoritmos.

A utilização de múltiplos *shots* evidencia a natureza probabilística da medição quântica.

---

# 7. Estados de Bell

Um dos principais experimentos consiste na construção de um **Par de Bell**, um estado maximamente emaranhado.

O circuito é composto essencialmente pelas portas:

- Hadamard;
- CNOT.

Partindo do estado

\[
|00\rangle,
\]

obtém-se

\[
|\Phi^+\rangle=
\frac{|00\rangle+|11\rangle}{\sqrt2}.
\]

Esse estado apresenta correlação perfeita entre os dois qubits, independentemente da distância entre eles, caracterizando o fenômeno de **emaranhamento quântico**.

---

# 8. Emaranhamento quântico

Os notebooks apresentam uma introdução prática ao emaranhamento.

São discutidos conceitos como:

- estados separáveis;
- estados não separáveis;
- correlação quântica;
- impossibilidade de descrição independente dos qubits.

A análise dos histogramas obtidos pelo simulador evidencia que apenas os estados

- 00
- 11

aparecem após a medição, conforme previsto teoricamente para o estado de Bell construído.

---

# 9. Medição quântica

Outro conceito explorado é o processo de medição.

Após a aplicação das portas quânticas, o sistema encontra-se em superposição.

Entretanto, ao medir os qubits, ocorre o colapso do vetor de estado para um dos estados da base computacional.

Os notebooks mostram que as frequências observadas convergem para as probabilidades previstas pelas amplitudes do vetor de estado, ilustrando empiricamente a Regra de Born.

---

# 10. Superdense Coding

A aula prática também apresenta uma introdução ao protocolo de **Superdense Coding**.

Esse protocolo demonstra que:

- um par previamente emaranhado;
- aliado ao envio físico de apenas um qubit;

permite transmitir **dois bits clássicos** de informação.

Embora simples, esse protocolo constitui uma das primeiras aplicações da informação quântica, explorando diretamente o recurso do emaranhamento.

---

# Técnicas computacionais utilizadas

Durante o desenvolvimento dos notebooks foram empregadas diversas funcionalidades do ecossistema Qiskit, incluindo:

- construção manual de circuitos;
- aplicação de portas unitárias;
- visualização gráfica de circuitos;
- obtenção do vetor de estado;
- representação na Esfera de Bloch;
- execução em simuladores;
- histogramas de medições;
- análise probabilística dos resultados.

Essas ferramentas aproximam a implementação computacional dos conceitos formais estudados em Teoria da Informação Quântica e Mecânica Quântica.

---

# Metodologia

Os notebooks seguem uma sequência didática baseada em quatro etapas:

1. apresentação da fundamentação teórica;
2. implementação computacional em Qiskit;
3. execução de experimentos simulados;
4. comparação entre teoria matemática e resultados obtidos.

Essa abordagem favorece uma aprendizagem progressiva, permitindo compreender simultaneamente os aspectos físicos, matemáticos e computacionais envolvidos.

---

# Competências desenvolvidas

Ao longo dos notebooks são exercitadas competências relacionadas a:

- programação científica em Python;
- modelagem de circuitos quânticos;
- álgebra linear aplicada à computação quântica;
- manipulação de vetores de estado;
- interpretação de probabilidades quânticas;
- visualização geométrica de qubits;
- utilização do framework Qiskit;
- desenvolvimento de experimentos reproduzíveis em ambiente Colab.

---

# Considerações finais

Este repositório representa uma introdução prática aos principais fundamentos da Computação Quântica utilizando o framework **Qiskit**. Os notebooks integram rigor matemático, interpretação física e implementação computacional para demonstrar conceitos como superposição, portas quânticas, representação na Esfera de Bloch, emaranhamento, estados de Bell e protocolos elementares de comunicação quântica. Ao combinar formalismo teórico com experimentação em simuladores, o material estabelece uma base sólida para estudos posteriores em algoritmos quânticos, teoria da informação quântica, correção de erros, criptografia quântica e arquiteturas de computadores quânticos.

---

## Referências

- Michael A. Nielsen, Isaac L. Chuang. **Quantum Computation and Quantum Information**.
- IBM Quantum Documentation.
- Qiskit Documentation.
- IBM Quantum Learning.
- Preskill, J. *Lecture Notes on Quantum Computation*.
