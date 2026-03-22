


import java.util.Scanner;

public class Hand{

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int opcao;

        do {
            System.out.println("\n===== MENU =====");
            System.out.println("0 - Sair");
            for (int i = 1; i <= 10; i++) {
                System.out.println(i + " - Exercício " + i);
            }
            System.out.print("Escolha uma opção: ");
            opcao = sc.nextInt();

            switch (opcao) {
                case 0:
                    System.out.println("Saindo...");
                    break;

                case 1:
                    exercicio1(sc);
                    break;
                case 2:
                    exercicio2(sc);
                    break;
                case 3:
                    exercicio3(sc);
                    break;
                case 4:
                    exercicio4(sc);
                    break;
                case 5:
                    exercicio5(sc);
                    break;
                case 6:
                    exercicio6(sc);
                    break;
                case 7:
                    exercicio7(sc);
                    break;
                case 8:
                    exercicio8(sc);
                    break;
                case 9:
                    exercicio9(sc);
                    break;
                case 10:
                    exercicio10(sc);
                    break;
                default:
                    System.out.println("Opção inválida!");
            }

        } while (opcao != 0);

        sc.close();
    }

    // Exercício 1 - Par ou Ímpar
    public static void exercicio1(Scanner sc) {
        System.out.print("Digite um número inteiro: ");
        int n = sc.nextInt();
        if (n % 2 == 0)
            System.out.println("PAR");
        else
            System.out.println("ÍMPAR");
    }

    // Exercício 2 - Maior de dois
    public static void exercicio2(Scanner sc) {
        System.out.print("Digite o primeiro número: ");
        int a = sc.nextInt();
        System.out.print("Digite o segundo número: ");
        int b = sc.nextInt();
        if (a > b)
            System.out.println("Maior: " + a);
        else if (b > a)
            System.out.println("Maior: " + b);
        else
            System.out.println("Iguais");
    }

    // Exercício 3 - Calculadora com menu
    public static void exercicio3(Scanner sc) {
        System.out.println("1 - Somar\n2 - Subtrair\n3 - Multiplicar\n4 - Dividir");
        System.out.print("Escolha a operação: ");
        int op = sc.nextInt();
        System.out.print("Digite o primeiro número: ");
        double n1 = sc.nextDouble();
        System.out.print("Digite o segundo número: ");
        double n2 = sc.nextDouble();
        double resultado;

        switch (op) {
            case 1:
                resultado = n1 + n2;
                System.out.println("Resultado: " + resultado);
                break;
            case 2:
                resultado = n1 - n2;
                System.out.println("Resultado: " + resultado);
                break;
            case 3:
                resultado = n1 * n2;
                System.out.println("Resultado: " + resultado);
                break;
            case 4:
                if (n2 == 0)
                    System.out.println("Erro: Divisão por zero!");
                else {
                    resultado = n1 / n2;
                    System.out.println("Resultado: " + resultado);
                }
                break;
            default:
                System.out.println("Opção inválida!");
        }
    }

    // Exercício 4 - Validação de entrada
    public static void exercicio4(Scanner sc) {
        int nota;
        do {
            System.out.print("Digite uma nota entre 0 e 100: ");
            nota = sc.nextInt();
        } while (nota < 0 || nota > 100);
        System.out.println("Nota válida: " + nota);
    }

    // Exercício 5 - Sentinela
    public static void exercicio5(Scanner sc) {
        int n, maior = Integer.MIN_VALUE, menor = Integer.MAX_VALUE;
        do {
            System.out.print("Digite um número (0 para sair): ");
            n = sc.nextInt();
            if (n != 0) {
                if (n > maior) maior = n;
                if (n < menor) menor = n;
            }
        } while (n != 0);

        if (maior == Integer.MIN_VALUE)
            System.out.println("Nenhum número foi digitado.");
        else
            System.out.println("Maior: " + maior + ", Menor: " + menor);
    }

    // Exercício 6 - Simulador de caixa
    public static void exercicio6(Scanner sc) {
        double saldo = 1000;
        int op;
        do {
            System.out.println("1 - Depositar\n2 - Sacar\n3 - Ver saldo\n4 - Sair");
            System.out.print("Escolha uma opção: ");
            op = sc.nextInt();
            switch (op) {
                case 1:
                    System.out.print("Valor a depositar: ");
                    double dep = sc.nextDouble();
                    if (dep > 0) {
                        saldo += dep;
                        System.out.println("Depósito realizado!");
                    } else {
                        System.out.println("Valor inválido!");
                    }
                    break;
                case 2:
                    System.out.print("Valor a sacar: ");
                    double saque = sc.nextDouble();
                    if (saque > 0 && saque <= saldo) {
                        saldo -= saque;
                        System.out.println("Saque realizado!");
                    } else {
                        System.out.println("Saque inválido!");
                    }
                    break;
                case 3:
                    System.out.println("Saldo: R$ " + saldo);
                    break;
                case 4:
                    System.out.println("Saindo...");
                    break;
                default:
                    System.out.println("Opção inválida!");
            }
        } while (op != 4);
        System.out.println("Saldo final: R$ " + saldo);
    }

    // Exercício 7 - Desconto por categoria
    public static void exercicio7(Scanner sc) {
        System.out.print("Valor da compra: R$ ");
        double valor = sc.nextDouble();
        System.out.print("Categoria do cliente (1 = comum, 2 = premium, 3 = funcionário): ");
        int cat = sc.nextInt();
        double desconto = 0;

        switch (cat) {
            case 1: desconto = 0.05; break;
            case 2: desconto = 0.10; break;
            case 3: desconto = 0.15; break;
            default:
                System.out.println("Categoria inválida!");
                return;
        }

        double valorDesconto = valor * desconto;
        double valorFinal = valor - valorDesconto;
        System.out.println("Desconto: R$ " + valorDesconto);
        System.out.println("Valor final a pagar: R$ " + valorFinal);
    }

    // Exercício 8 - Contagem de valores
    public static void exercicio8(Scanner sc) {
        int positivos = 0, negativos = 0, zeros = 0;
        for (int i = 0; i < 10; i++) {
            System.out.print("Digite um número inteiro: ");
            int n = sc.nextInt();
            if (n > 0) positivos++;
            else if (n < 0) negativos++;
            else zeros++;
        }
        System.out.println("Positivos: " + positivos);
        System.out.println("Negativos: " + negativos);
        System.out.println("Zeros: " + zeros);
    }

    // Exercício 9 - Soma de 1 até N
    public static void exercicio9(Scanner sc) {
        System.out.print("Digite N: ");
        int N = sc.nextInt();
        int soma = 0;
        for (int i = 1; i <= N; i++) {
            soma += i;
        }
        System.out.println("Soma de 1 até " + N + " = " + soma);
    }

    // Exercício 10 - Contagem regressiva e soma
    public static void exercicio10(Scanner sc) {
        System.out.print("Digite N (>0): ");
        int N = sc.nextInt();
        if (N <= 0) {
            System.out.println("Número inválido!");
            return;
        }
        int soma = 0;
        for (int i = N; i >= 1; i--) {
            System.out.print(i + " ");
            soma += i;
        }
        System.out.println("\nSoma = " + soma);
    }
}
