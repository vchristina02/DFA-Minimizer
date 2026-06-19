# Minimizador de Autômatos (DFA)

Este projeto é um **Minimizador de Autômatos Finitos Determinísticos (DFA)** desenvolvido em Java com interface gráfica (Swing). O objetivo do programa é ler a estrutura de um autômato a partir de um arquivo de texto, calcular quais estados são equivalentes e exibir visualmente a matriz de minimização.

## Exemplos de Teste
Na pasta **`assets/`** da raiz do projeto, você encontrará vários arquivos de exemplo (como `automato.dat`, `automato2.dat`, etc.) prontos para testar diferentes cenários de minimização (fusão de estados finais, loops e autômatos maiores).

## Pré-requisitos
- **Java (JDK):** Versão 17 ou superior.

## Como Rodar

Abra o terminal na pasta principal do projeto e use os comandos abaixo:

### 1. Compilar o código
Como o programa usa o símbolo `Ø` na matriz, é necessário compilar forçando o formato UTF-8:
```bash
javac -encoding UTF-8 -d build/classes src/program/*.java

```

### 2. Executar diretamente

```bash
java -cp build/classes program.Program

```

### 3. Criar e rodar o arquivo executável (.jar)

Se preferir gerar um arquivo único para rodar mais fácil:

```bash
# Cria o arquivo JAR
jar cfe MeuAutomato.jar program.Program -C build/classes/ .

# Executa o JAR
java -jar MeuAutomato.jar

```

## Estrutura do Arquivo (.dat)

Para testar novos autômatos, configure o arquivo dentro de `assets/` seguindo este modelo:

```text
Q,q0,q1,q2       <- Lista de estados (o primeiro caractere antes da vírgula é ignorado)
0,1              <- Símbolos do alfabeto
q0,0,q1          <- Transições (origem, símbolo, destino)
q0,1,q2
>                <- Caractere '>' sozinho para parar as transições
>q0              <- Estado inicial (com '>' na frente)
*q1,q2           <- Estados finais (com '*' na frente)

```
