<h2>📌Comentário - Primeiro parágrafo</h2>

<p>O texto diferencia programação, ciência da computação e engenharia de software, destacando que esta última aplica teoria e práticas de forma rigorosa para criar sistemas grandes e confiáveis. Embora o software hoje exige padrões mais robustos, dado seu papel crítico na sociedade. A experiência do Google com sistemas massivos oferece uma visão prática única sobre como alcançar essa maturidade.</p>

<h2>📌Comentário - Segundo parágrafo</h2>

<p>Esse segundo trecho amplia a definição de engenharia de software, deixando claro que ela não é só escrever código, mas também envolve processos, ferramentas e práticas que permitem manter esse código útil e sustentável ao longo do tempo.

O Google propõe a ideia de que engenharia de software é como “programação integrada ao longo do tempo”, ou seja, não basta o código funcionar hoje; ele precisa ser fácil de evoluir, corrigir e eventualmente aposentar.

O texto apresenta três princípios centrais para guiar decisões e práticas:
<p>1.	Tempo e Mudança – O código inevitavelmente precisará se adaptar a novas necessidades, tecnologias e requisitos ao longo de sua vida.</p>
<p>2.	Escala e Crescimento – À medida que a organização e o produto crescem, processos e arquitetura também precisam evoluir.</p>
<p>3.	Trade-offs e Custos – Decisões devem ser tomadas considerando os impactos no longo prazo e o equilíbrio entre vantagens e desvantagens.</p>

<h2>📌Exemplos de trade-offs em engenharia de software:</h2>

<p>1.	Velocidade de entrega vs. Qualidade do código</p>
<p>•	Escolher entregar rapidamente pode ajudar a lançar uma funcionalidade no mercado, mas aumenta o risco de dívidas técnicas e problemas futuros.</p>
<p>•	Optar por investir mais tempo na qualidade reduz problemas a longo prazo, mas pode atrasar o lançamento.</p>

<p>2.	Performance vs. Legibilidade</p>
<p>•	Um código extremamente otimizado pode ser mais rápido, mas também mais complexo e difícil de entender.</p>
<p>•	Um código mais simples e legível é fácil de manter, mas pode não ser o mais eficiente em execução.</p>

<p>3.	Centralização vs. Descentralização de decisões técnicas</p>
<p>•	Centralizar decisões traz padronização e consistência, mas pode reduzir a autonomia e a agilidade das equipes.</p>
<p>•	Descentralizar dá mais liberdade e velocidade para cada time, mas pode gerar fragmentação e duplicação de esforços.</p>

<h2>📌Diagrama de Classes UML - Sistema Biblioteca</h2>

<img width="2328" height="1540" alt="image" src="https://github.com/user-attachments/assets/68114b2b-815e-4672-9ce7-a447c4a60afa" />

<h2>📌Código Java</h2>

<code>// Classe Pessoa
public class Pessoa {
    private String nome;
    private int idade;

    // Construtor
    public Pessoa(String nome, int idade) {
        this.nome = nome;
        this.idade = idade;
    }

    // Getters e Setters
    public String getNome() {
        return nome;
    }

    public void setNome(String nome) {
        this.nome = nome;
    }

    public int getIdade() {
        return idade;
    }

    public void setIdade(int idade) {
        this.idade = idade;
    }

    // Métodos
    public void falar() {
        System.out.println(nome + " está falando.");
    }

    public void andar() {
        System.out.println(nome + " está andando.");
    }
}

// Classe Aluno (herda de Pessoa)
public class Aluno extends Pessoa {
    private String matricula;

    public Aluno(String nome, int idade, String matricula) {
        super(nome, idade);
        this.matricula = matricula;
    }

    public String getMatricula() {
        return matricula;
    }

    public void setMatricula(String matricula) {
        this.matricula = matricula;
    }

    public void estudar() {
        System.out.println(getNome() + " está estudando.");
    }
}

// Classe Professor (herda de Pessoa)
public class Professor extends Pessoa {
    private double salario;

    public Professor(String nome, int idade, double salario) {
        super(nome, idade);
        this.salario = salario;
    }

    public double getSalario() {
        return salario;
    }

    public void setSalario(double salario) {
        this.salario = salario;
    }

    public void ensinar() {
        System.out.println(getNome() + " está ensinando.");
    }
}
</code>

<h2>📌Exemplo 2 de Diagrama de Classes UML - Sistema Bancário</h2>

<img width="2244" height="576" alt="image" src="https://github.com/user-attachments/assets/65f6a9cc-0971-4bf0-a6da-9e4a603f0ded" />

<h2>📌Código Java</h2>

<code>
import java.util.ArrayList;
import java.util.List;

class Banco {
    private String numero;
    private String nome;
    private String endereco;

    // Construtor
    public Banco(String numero, String nome, String endereco) {
        this.numero = numero;
        this.nome = nome;
        this.endereco = endereco;
    }

    // Getters e Setters
    public String getNumero() {
        return numero;
    }

    public void setNumero(String numero) {
        this.numero = numero;
    }

    public String getNome() {
        return nome;
    }

    public void setNome(String nome) {
        this.nome = nome;
    }

    public String getEndereco() {
        return endereco;
    }

    public void setEndereco(String endereco) {
        this.endereco = endereco;
    }

    @Override
    public String toString() {
        return "Banco{" +
                "numero='" + numero + '\'' +
                ", nome='" + nome + '\'' +
                ", endereco='" + endereco + '\'' +
                '}';
    }
}

class SistemaBancario {
    private List<Banco> bancos;

    public SistemaBancario() {
        this.bancos = new ArrayList<>();
    }

    // Método para adicionar banco
    public void addBanco(Banco banco) {
        bancos.add(banco);
    }

    // Método para buscar banco por número
    public List<Banco> buscarBancoNumero(String numero) {
        List<Banco> resultado = new ArrayList<>();
        for (Banco banco : bancos) {
            if (banco.getNumero().equals(numero)) {
                resultado.add(banco);
            }
        }
        return resultado;
    }
}

// Classe de teste
public class Main {
    public static void main(String[] args) {
        SistemaBancario sistema = new SistemaBancario();

        Banco b1 = new Banco("001", "Banco do Brasil", "Brasília");
        Banco b2 = new Banco("237", "Bradesco", "São Paulo");
        Banco b3 = new Banco("001", "Banco do Brasil - Filial", "Rio de Janeiro");

        sistema.addBanco(b1);
        sistema.addBanco(b2);
        sistema.addBanco(b3);

        System.out.println("Buscando bancos com número 001:");
        List<Banco> encontrados = sistema.buscarBancoNumero("001");
        for (Banco b : encontrados) {
            System.out.println(b);
        }
    }
}

</code>
