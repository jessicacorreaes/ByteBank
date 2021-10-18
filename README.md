# Classe Funcionario
```
import groovy.lang.GString;

public class Funcionario {

    private String nome;
    private String cpf;
    private double salario;


    public double getBonificacao() {
        return this.salario * 0.05;
    }

       public String getNome () {
           return nome;
       }
        public void setNome (String nome){
            this.nome = nome;
        }
        public String getCpf () {
            return cpf;
        }
        public void setCpf (String cpf){
            this.cpf = cpf;
        }
        public double getSalario () {
            return salario;
        }
        public void setSalario ( double salario){
            this.salario = salario;
        }
    }
```
#Classe  Gerente

```
public class Gerente extends Funcionario {

    private int senha;

    public void setSenha(int senha) {
        this.senha = senha;
    }

    public boolean autentica(int senha) {
        if(this.senha == senha) {
            return true;
        } else {
            return false;
        }
    }

    public double getBonificacao() {
        return super.getBonificacao() + super.getSalario();
    }
}
```
# Testa Referencia
```
public class TesteReferencias {
    public static void main(String[] args) {

        Funcionario g1 = new Gerente();

        g1.setNome("Marcos");
        String nome = g1.getNome();

       // g1.autentica(222);

        System.out.println(nome);
    }
}

```
# Testa Funcionario
```
public class TesteFuncionario {

    public static void main(String[] args) {

        Funcionario nico = new Funcionario();
        nico.setNome("Nico Steppat");
        nico.setCpf("223355646-9");
        nico.setSalario(2600.00);

        System.out.println(nico.getNome());
        System.out.println(nico.getBonificacao());

        //nico.salario = 300.0;

    }

}

```
#Testa Gerente
```
public class TesteGerente {

    public static void main(String [] args) {
        Gerente g1 = new Gerente();
        g1.setNome("Marco");
        g1.setCpf("23556813");
        g1.setSalario(5000.0);

        System.out.println(g1.getNome());
        System.out.println(g1.getCpf());
        System.out.println(g1.getSalario());

        g1.setSenha(2222);
        boolean autenticou = g1.autentica(2222);

        System.out.println(autenticou);

        System.out.println(g1.getBonificacao());

    }

}
```
