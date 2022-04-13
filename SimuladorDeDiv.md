# CalculadoraDeDividendos

public class SimuladorDeDivs {
    public static void main(String[] args) {
        Scanner entrada = new Scanner(System.in);

        Ativo ativo1 = new Ativo("MXRF11", 0.1, 9.55);
        Ativo ativo3 = new Ativo("RECR11", 1.2, 102.27);
        Ativo ativo4 = new Ativo("HGLG11", 1.1, 164.99);

        System.out.println(ativo1.imprime());
        System.out.println("---------------------------------");
        System.out.println(ativo4.imprime());
        System.out.println("---------------------------------");
        System.out.println(ativo3.imprime());
        System.out.println("---------------------------------");

        System.out.print("Quanto vai investir: ");
        double valorInvestir = entrada.nextDouble();
        System.out.println("---------------------------------");

        System.out.print("Digite o numero de cotas do fundo MXRF11: ");
        int numDeCotasMXRF = entrada.nextInt();
        System.out.print("Digite o numero de cotas do fundo HGLG11: ");
        int numDeCotasHGLG = entrada.nextInt();
        System.out.print("Digite o numero de cotas do fundo RECR11: ");
        int numDeCotasRECR = entrada.nextInt();

        double divMXRF = numDeCotasMXRF * ativo1.ultimoDividendo;
        double divHGLG = numDeCotasHGLG * ativo4.ultimoDividendo;
        double divRECR = numDeCotasRECR * ativo3.ultimoDividendo;
        double divTotal = divMXRF + divRECR + divHGLG;

        System.out.println("---------------------------------");
        System.out.println("Dividendo do ativo MXRF11: R " + divMXRF + "$");
        System.out.println("Dividendo do ativo HGLG11: R " + divHGLG + "$");
        System.out.println("Dividendo do ativo RECR11: R " + divRECR + "$");
        System.out.println("---------------------------------");
        System.out.println("Total de dividendos: R " + divTotal + "$");

        double valorGastoMXRF = ativo1.precoDoAtivo * numDeCotasMXRF;
        double valorGastoHGLG = ativo4.precoDoAtivo * numDeCotasHGLG;
        double valorGastoRECR = ativo3.precoDoAtivo * numDeCotasRECR;
        double valorGastoTotal = valorGastoMXRF + valorGastoHGLG + valorGastoRECR;
        System.out.println("---------------------------------");
        System.out.printf("Valor a ser gasto com o fundo MXRF11: R$ %.2f" , valorGastoMXRF);
        System.out.printf("\nValor a ser gasto com o fundo HGLG11: R$ %.2f" , valorGastoHGLG);
        System.out.printf("\nValor a ser gasto com o fundo RECR11: R$ %.2f" , valorGastoRECR);
        System.out.printf("\nValor a gasto no total: R$ %.2f" , valorGastoTotal);
        double margemDeErro = valorInvestir - valorGastoTotal;
        System.out.printf("\nMargem de  erro: R$ %.2f" , margemDeErro);
        entrada.close();
    }
}
