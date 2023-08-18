# Conta-bancaria
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {

        Scanner leitura = new Scanner(System.in);
        Conta conta = new Conta();
        {


            System.out.println("Digite seu nome? ");
            conta.setNome(leitura.nextLine());
            System.out.println("Digite o tipo da conta ");
            conta.setConta(leitura.nextLine());
            System.out.println("Digite o saldo inicial ");
            conta.setSaldo(leitura.nextDouble());


            String extrato = """
                    *********************************************
                    Dados iniciais do cliente:
                                    
                    Nome: %s
                    Tipo conta: %s
                    Saldo inicial: R$ %.2f
                    *********************************************
                                    
                    """.formatted(conta.getNome(), conta.getConta(), conta.getSaldo());

            String operacoes = """
                    Operações
                                    
                    1- Consultar saldo
                    2- Receber valor
                    3- Tranferir valor
                    4- Sair
                                    
                    Digite a opção desejada:
                    """;
            System.out.println(extrato);
            int caso = 0;
            double valor = 0;
            while (caso < 4) {
                System.out.println(operacoes);
                caso = leitura.nextInt();
                if (caso == 1) {
                    System.out.println("O saldo atual é R$ " + conta.getSaldo());
                }
                if (caso == 2) {
                    System.out.println("Informe o valor a receber: ");
                    conta.recebe(valor = leitura.nextDouble());
                }
                if (caso == 3) {
                    System.out.println("Informe o valor que deseja tranferir: ");
                    conta.transfere(valor = leitura.nextDouble());
                }
                if (caso == 4) {
                    System.out.println("Saindo...");
                }
            }
        }
    }
}
