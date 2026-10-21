# hand-on-30-09
atividade da faculdade 
01 public class Ex01 {
    public static void main(String[] args) {
        int idade = Entrada.lerInt("Idade do jogador: ");
        int horas = Entrada.lerInt("Horas jogadas por semana: ");

        String classificacao;
        if (idade < 12) {
            classificacao = "Jogador Mirim";
        } else if (idade <= 17) {
            classificacao = horas <= 10 ? "Jogador Casual" : "Jogador Frequente";
        } else if (horas <= 5) {
            classificacao = "Jogador Casual";
        } else if (horas <= 15) {
            classificacao = "Jogador Gamer";
        } else {
            classificacao = "Gamer Hardcore";
        }
        System.out.println(classificacao);
    }
}

02 public class Ex02 {
    public static void main(String[] args) {
        int opcao;
        do {
            System.out.println();
            System.out.println("===== STREAMING =====");
            System.out.println();
            System.out.println("1 - Netflix");
            System.out.println("2 - Disney+");
            System.out.println("3 - Prime Video");
            System.out.println("4 - Spotify");
            System.out.println("5 - Sair");
            System.out.println();
            opcao = Entrada.lerInt("Escolha uma opção: ");

            switch (opcao) {
                case 1 -> {
                    System.out.println("Você escolheu Netflix.");
                    System.out.println("Prepare a pipoca!");
                }
                case 2 -> {
                    System.out.println("Você escolheu Disney+.");
                    System.out.println("Hora da magia!");
                }
                case 3 -> {
                    System.out.println("Você escolheu Prime Video.");
                    System.out.println("Bora maratonar!");
                }
                case 4 -> {
                    System.out.println("Você escolheu Spotify.");
                    System.out.println("Aumenta o som!");
                }
                case 5 -> System.out.println("Até a próxima!");
                default -> System.out.println("Opção inválida.");
            }
        } while (opcao != 5);
    }
}

03 public class Ex03 {
    public static void main(String[] args) {
        final String SENHA_CORRETA = "1234";
        int tentativas = 0;
        String senha;
        do {
            System.out.println();
            senha = Entrada.lerTexto("Digite sua senha:\n");
            tentativas++;
            if (!senha.equals(SENHA_CORRETA)) {
                System.out.println("Senha incorreta.");
            }
        } while (!senha.equals(SENHA_CORRETA));

        System.out.println();
        System.out.println("Login realizado com sucesso!");
        System.out.println("Login realizado após " + tentativas + " tentativas.");
    }
}

04 public class Ex04 {
    public static void main(String[] args) {
        int idade = Entrada.lerInt("Digite sua idade:\n");
        int ingresso = lerSimNao("Possui ingresso?\n1 - Sim\n2 - Não\n");

        if (ingresso == 2) {
            System.out.println("Entrada negada: ingresso obrigatório.");
        } else if (idade >= 18) {
            System.out.println("Entrada liberada!");
        } else {
            int responsavel = lerSimNao("Está acompanhado de um responsável?\n1 - Sim\n2 - Não\n");
            if (responsavel == 1) {
                System.out.println("Entrada liberada!");
            } else {
                System.out.println("Entrada negada: menor de idade desacompanhado.");
            }
        }
    }

    private static int lerSimNao(String pergunta) {
        int r;
        do {
            r = Entrada.lerInt(pergunta);
            if (r != 1 && r != 2) System.out.println("Opção inválida.");
        } while (r != 1 && r != 2);
        return r;
    }
}
05 public class Ex05 {
    public static void main(String[] args) {
        double dinheiro = Entrada.lerDouble("Quanto dinheiro você possui?\n");
        int chuva;
        do {
            chuva = Entrada.lerInt("Está chovendo?\n\n1 - Sim\n2 - Não\n");
        } while (chuva != 1 && chuva != 2);

        if (dinheiro < 20) {
            System.out.println("Rolê em casa.");
        } else if (dinheiro < 50) {
            System.out.println(chuva == 1 ? "Streaming + comida." : "Praça ou parque.");
        } else if (dinheiro < 100) {
            System.out.println("Cinema.");
        } else {
            int idade = Entrada.lerInt("Qual a sua idade?\n");
            if (idade < 18) {
                System.out.println("Shopping + cinema.");
            } else {
                System.out.println("Show, restaurante ou churrasco com a galera.");
            }
        }
    }
}

06 public class Ex06 {
    public static void main(String[] args) {
        int saldo = 1500;
        String[] nomes = {"", "Básica", "Rara", "Épica", "Lendária"};
        int[] precos = {0, 100, 250, 500, 1000};
        int opcao;
        do {
            System.out.println();
            System.out.println("===== LOJA DE SKINS =====");
            System.out.println();
            System.out.println("1 - Skin Básica   - 100 moedas");
            System.out.println("2 - Skin Rara     - 250 moedas");
            System.out.println("3 - Skin Épica    - 500 moedas");
            System.out.println("4 - Skin Lendária - 1000 moedas");
            System.out.println("0 - Sair");
            System.out.println();
            System.out.println("Saldo: " + saldo + " moedas");
            System.out.println();
            opcao = Entrada.lerInt("Escolha uma skin:\n");

            if (opcao == 0) {
                System.out.println("Até a próxima!");
            } else if (opcao < 0 || opcao > 4) {
                System.out.println("Opção inválida.");
            } else if (saldo < precos[opcao]) {
                System.out.println("Saldo insuficiente.");
            } else {
                saldo -= precos[opcao];
                System.out.println("Skin " + nomes[opcao] + " comprada!");
                System.out.println();
                System.out.println("Saldo restante: " + saldo + " moedas");
            }
        } while (opcao != 0);
    }
}

07 public class Ex07 {
    public static void main(String[] args) {
        String[] nomes = {"", "Pizza", "Hambúrguer", "Batata", "Refrigerante"};
        double[] precos = {0, 30.00, 20.00, 12.00, 8.00};
        double total = 0;
        int opcao;
        do {
            System.out.println();
            System.out.println("===== LANCHONETE =====");
            System.out.println();
            System.out.println("1 - Pizza         - R$ 30,00");
            System.out.println("2 - Hambúrguer    - R$ 20,00");
            System.out.println("3 - Batata        - R$ 12,00");
            System.out.println("4 - Refrigerante  - R$ 8,00");
            System.out.println("0 - Finalizar");
            System.out.println();
            opcao = Entrada.lerInt("Escolha uma opção: ");

            if (opcao >= 1 && opcao <= 4) {
                total += precos[opcao];
                System.out.printf("%s adicionado(a). Total parcial: R$ %.2f%n", nomes[opcao], total);
            } else if (opcao != 0) {
                System.out.println("Opção inválida.");
            }
        } while (opcao != 0);

        System.out.printf("%nValor do pedido: R$ %.2f%n", total);
        double desconto;
        if (total < 50) {
            desconto = 0;
            System.out.println("Sem desconto.");
        } else if (total < 100) {
            desconto = 0.05;
            System.out.println("5% de desconto.");
        } else {
            int estudante;
            do {
                estudante = Entrada.lerInt("Você é estudante?\n\n1 - Sim\n2 - Não\n");
            } while (estudante != 1 && estudante != 2);
            desconto = estudante == 1 ? 0.15 : 0.10;
            System.out.println(estudante == 1 ? "15% de desconto." : "10% de desconto.");
        }
        System.out.printf("Total a pagar: R$ %.2f%n", total * (1 - desconto));
    }
}
08 import java.util.Random;

public class Ex08 {
    public static void main(String[] args) {
        Random random = new Random();
        int vidas1 = 3, vidas2 = 3;
        int pontos1 = 0, pontos2 = 0;
        int rodada = 0;

        while (vidas1 > 0 && vidas2 > 0) {
            rodada++;
            int n1 = random.nextInt(10) + 1;
            int n2 = random.nextInt(10) + 1;

            System.out.println("===== RODADA " + rodada + " =====");
            System.out.println();
            System.out.println("Jogador 1 tirou: " + n1);
            System.out.println("Jogador 2 tirou: " + n2);
            System.out.println();

            if (n1 > n2) {
                pontos1 += 10;
                vidas2--;
                System.out.println("Jogador 1 venceu a rodada!");
                System.out.println("Jogador 2 perdeu uma vida!");
            } else if (n2 > n1) {
                pontos2 += 10;
                vidas1--;
                System.out.println("Jogador 2 venceu a rodada!");
                System.out.println("Jogador 1 perdeu uma vida!");
            } else {
                pontos1 += 5;
                pontos2 += 5;
                System.out.println("Empate!");
                System.out.println("Ninguém perdeu vida.");
                System.out.println();
                System.out.println("Cada jogador recebeu 5 pontos.");
            }
            System.out.println();
            System.out.println("Vidas do Jogador 1: " + vidas1);
            System.out.println("Pontos do Jogador 1: " + pontos1);
            System.out.println();
            System.out.println("Vidas do Jogador 2: " + vidas2);
            System.out.println("Pontos do Jogador 2: " + pontos2);
            System.out.println();
        }

        System.out.println("===== RESULTADO FINAL =====");
        System.out.println();
        System.out.println("Jogador 1");
        System.out.println("Vidas: " + vidas1);
        System.out.println("Pontos: " + pontos1);
        System.out.println();
        System.out.println("Jogador 2");
        System.out.println("Vidas: " + vidas2);
        System.out.println("Pontos: " + pontos2);
        System.out.println();
        System.out.println("Vencedor: " + (vidas1 > 0 ? "Jogador 1" : "Jogador 2"));
    }
}
