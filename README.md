import java.util.Scanner;

class ContaBancaria {

private double saldo;
private double limiteChequeEspecial;

public ContaBancaria(double depositoInicial) {
saldo = depositoInicial;

if (depositoInicial <= 500) {    
    limiteChequeEspecial = 50;    
} else {    
    limiteChequeEspecial = depositoInicial * 0.50;    
}

}

public void consultarSaldo() {
System.out.println("Saldo: R$ " + saldo);
}

public void consultarChequeEspecial() {
System.out.println("Limite: R$ " + limiteChequeEspecial);
}

public void depositar(double valor) {
if (valor > 0) {
saldo += valor;
System.out.println("Deposito realizado!");
} else {
System.out.println("Valor invalido!");
}
}

public void sacar(double valor) {
if (valor > 0 && valor <= saldo + limiteChequeEspecial) {
saldo -= valor;
System.out.println("Saque realizado!");
} else {
System.out.println("Saldo insuficiente!");
}
}

public void pagarBoleto(double valor) {
sacar(valor);
}

public void verificarChequeEspecial() {
if (saldo < 0) {
System.out.println("Voce esta usando o cheque especial.");
} else {
System.out.println("Voce nao esta usando o cheque especial.");
}
}

}

public class Main {

public static void main(String[] args) {

Scanner entrada = new Scanner(System.in);    

System.out.print("Digite o deposito inicial: ");    
double deposito = entrada.nextDouble();    

ContaBancaria conta = new ContaBancaria(deposito);    

conta.consultarSaldo();    
conta.consultarChequeEspecial();    

System.out.print("Digite o valor do saque: ");    
double saque = entrada.nextDouble();    

conta.sacar(saque);    

conta.consultarSaldo();    
conta.verificarChequeEspecial();    

entrada.close();

}

}# meus-exercicios-java
Souza
