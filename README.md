import java.util.Random;
import java.util.Scanner;

public class LotoFacil {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        Random random = new Random();

        int opcao;
        do {
            System.out.println("**************************");
            System.out.println("Menu LOTOFÁCIL:");
            System.out.println("1) Apostar de 0 a 100");
            System.out.println("2) Apostar de A à Z");
            System.out.println("3) Apostar em par ou ímpar");
            System.out.println("0) Sair");
            System.out.println("**************************");
            System.out.print("Escolha uma opção: ");
            opcao = scanner.nextInt();

            switch (opcao) {
                case 1:
                    apostarDe0a100(scanner, random);
                    break;
                case 2:
                    apostarDeAaZ(scanner);
                    break;
                case 3:
                    apostarParOuImpar(scanner);
                    break;
                case 0:
                    System.out.println("Saindo...");
                    break;
                default:
                    System.out.println("Opção inválida.");
            }
        } while (opcao != 0);

        scanner.close();
    }

    public static void apostarDe0a100(Scanner scanner, Random random) {
        System.out.print("Digite um número de 0 a 100: ");
        int numeroApostado = scanner.nextInt();

        if (numeroApostado < 0 || numeroApostado > 100) {
            System.out.println("Aposta inválida.");
            return;
        }

        int numeroSorteado = random.nextInt(101);

        if (numeroApostado == numeroSorteado) {
            System.out.println("Você ganhou R$ 1.000,00 reais.");
        } else {
            System.out.println("Que pena! O número sorteado foi: " + numeroSorteado + ".");
        }
    }

    public static void apostarDeAaZ(Scanner scanner) {
        System.out.print("Digite uma letra de A à Z: ");
        char letraApostada = scanner.next().toUpperCase().charAt(0);

        if (!Character.isLetter(letraApostada)) {
            System.out.println("Aposta inválida.");
            return;
        }

        char letraPremiada = 'J'; // Exemplo: Letra premiada é 'J'

        if (letraApostada == letraPremiada) {
            System.out.println("Você ganhou R$ 500,00 reais.");
        } else {
            System.out.println("Que pena! A letra sorteada foi: " + letraPremiada + ".");
        }
    }

    public static void apostarParOuImpar(Scanner scanner) {
        System.out.print("Digite um número inteiro: ");
        int numeroDigitado = scanner.nextInt();

        if (numeroDigitado % 2 == 0) {
            System.out.println("Você ganhou R$ 100,00 reais.");
        } else {
            System.out.println("Que pena! O número digitado é ímpar e a premiação foi para números pares.");
        }
    }


}

