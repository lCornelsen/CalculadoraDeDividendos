public class Ativo {
    String nome;
    double ultimoDividendo;
    int numDeCotas;
    double precoDoAtivo;

    public Ativo() {

    }

    public Ativo(String nome, double ultimoDividendo, double precoDoAtivo) {
        this.nome = nome;
        this.ultimoDividendo = ultimoDividendo;
        this.precoDoAtivo = precoDoAtivo;
    }

    public String imprime() {
        return String.format("Nome do ativo: " + this.nome + "\nUltimo dividendo: R " + this.ultimoDividendo + "$" +
                "\nPreço da cota do ativo: R " + this.precoDoAtivo + "$");
    }

}
