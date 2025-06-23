# 🚀 Desafio Controle de Fluxo - DIO - Trilha Java Básico

Projeto proposto no curso da [DIO - Digital Innovation One](https://www.dio.me) na **Trilha de Java Básico**, ministrado por **Gleyson Sampaio**.

## 📚 Descrição

O objetivo deste desafio é exercitar os conhecimentos adquiridos no módulo de **Controle de Fluxo** em Java, implementando uma aplicação simples que recebe dois parâmetros via terminal e executa uma contagem baseada nesses valores.

## 🧠 Regras do Desafio

- O sistema deve receber **dois parâmetros inteiros** via terminal.
- Com esses dois números, o programa calculará a quantidade de interações necessárias usando um laço `for` e imprimirá os números de forma crescente.
- Exemplo:
  - Se os números digitados forem `12` e `30`, o programa deverá realizar `18` interações e imprimir:
    ```
    Imprimindo o número 1
    Imprimindo o número 2
    ...
    Imprimindo o número 18
    ```
- Caso o **primeiro parâmetro seja maior** que o segundo, deverá ser lançada uma **exceção customizada** chamada `ParametrosInvalidosException` com a mensagem:
  > "O segundo parâmetro deve ser maior que o primeiro"

## 🛠️ Estrutura do Projeto

- `Contador.java`: Classe principal onde toda a lógica do programa é implementada.
- `ParametrosInvalidosException.java`: Classe que representa a exceção personalizada para regras de negócio.

## 💡 Exemplo de Código

```java
public class Contador {
    public static void main(String[] args) {
        Scanner terminal = new Scanner(System.in);
        System.out.println("Digite o primeiro parâmetro");
        int parametroUm = terminal.nextInt();

        System.out.println("Digite o segundo parâmetro");
        int parametroDois = terminal.nextInt();

        try {
            contar(parametroUm, parametroDois);
        } catch (ParametrosInvalidosException exception) {
            System.out.println("O segundo parâmetro deve ser maior que o primeiro");
        }
    }

    static void contar(int parametroUm, int parametroDois) throws ParametrosInvalidosException {
        if (parametroUm >= parametroDois) {
            throw new ParametrosInvalidosException("O segundo parâmetro deve ser maior que o primeiro");
        }

        int contagem = parametroDois - parametroUm;
        for (int i = 1; i <= contagem; i++) {
            System.out.println("Imprimindo o número " + i);
        }
    }
}
# controle-fluxo-dio
Desafio da DIO controle de fluxo
