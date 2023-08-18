# Conta-bancaria
  public class Conta {
    private String nome;
    private String conta;
    private double saldo;


    public String getNome() {
        return nome;
    }

    public void setNome(String nome) {
        this.nome = nome;
    }

    public String getConta() {
        return conta;
    }

    public void setConta(String conta) {
        this.conta = conta;
    }

    public double getSaldo() {
        return saldo;
    }

    public void setSaldo(double saldo) {
        this.saldo = saldo;
    }

    public void recebe(double valor){
        this.saldo += valor;
        System.out.println("Saldo atualizado R$ " + (getSaldo()));
    }
    public void transfere(double valor){
        if (valor > this.saldo){
            System.out.println("Não há saldo suficiente para fazer essa tranferência, tente novamente!");
        } else {
            this.saldo -= valor;
            System.out.println("Saldo atualizado R$ " + (getSaldo()));
        }
    }
}
