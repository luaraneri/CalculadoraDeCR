#include <stdio.h>
#include <string.h>
#include <stdlib.h>
#include <ctype.h>





int w = 10;

struct listaMaterias { ////Struct para as matérias obrigatórias e seus créditos
    char nome [100];
    int creditos;
};
typedef struct listaMaterias listaMaterias;
listaMaterias materias[48];

struct alunosRAs { ////Lista para os RAs
    int qntd;
    int RA[10];
};
typedef struct alunosRAs RAs;

struct historicoAlunos { ////Struct para armazenas os códigos das matérias e os conceitos obtidos
    int codigoMat[41];
    char nota[41];
};
typedef struct historicoAlunos historicoAlunos;

RAs *criar_Lista() { ////Criando lista RAs
    RAs *alunoRA;
    alunoRA = (RAs *) malloc(sizeof (RAs));

    if (alunoRA != NULL) {
        alunoRA->qntd = 0;
    }

    return alunoRA;
}

int procuraRA(RAs *alunoRA, int buscaRA) ////Procura por BubbleSearch o RA na lista alunoRA
{
    int i = 0, resp = 0;
    if (alunoRA == NULL) {
        return -2;
    } else {
        while (i < alunoRA->qntd && alunoRA->RA[i] != buscaRA) {
            i++;
        }
        if (i == alunoRA->qntd) {
            return -1;
        } else {
            return i;
        }
    }
}

int adicionaRA(RAs *alunoRA, int RA) ////Adiciona RA no banco de dados
{
    if (alunoRA == NULL) {
        return -2;
    } else {
        if (alunoRA->qntd == w) {
            return -1;
        } else {
            alunoRA->RA[alunoRA->qntd] = RA;
            alunoRA->qntd++;
            return 1;
        }
    }
}


void adcMateria(historicoAlunos *historico, int posAluno);
void delMateria(historicoAlunos *historico, int posAluno);
void listarMaterias(historicoAlunos *historico, int posAluno);
void calculCR(historicoAlunos *historico, int posAluno);
void encontraOpcao(historicoAlunos *historico, int posAluno, int opcao);
void materiasBI(int opcao);

int main() {


    ////DECLARANDO MATÉRIAS OBRIGATÓRIAS DO BCT E BCH
    strcpy(materias[0].nome, "Fenômenos Mecânicos");
    materias[0].creditos = 5;
    strcpy(materias[1].nome, "Fenômenos Térmicos");
    materias[1].creditos = 4;
    strcpy(materias[2].nome, "Fenômenos Eletromagnéticos");
    materias[2].creditos = 5;
    strcpy(materias[3].nome, "Bases Conceituais da Energia");
    materias[3].creditos = 2;
    strcpy(materias[4].nome, "Evolução e Diversificação da Vida na Terra");
    materias[4].creditos = 3;
    strcpy(materias[5].nome, "Transformações Química");
    materias[5].creditos = 5;
    strcpy(materias[6].nome, "Biodiversidade: Interações entre organismos e ambiente");
    materias[6].creditos = 3;
    strcpy(materias[7].nome, "Geometria Analítica");
    materias[7].creditos = 3;
    strcpy(materias[8].nome, "Funções de Uma Variável");
    materias[8].creditos = 4;
    strcpy(materias[9].nome, "Funções de Várias Variáveis ");
    materias[9].creditos = 4;
    strcpy(materias[10].nome, "Introdução às Equações Diferenciais Ordinárias");
    materias[10].creditos = 4;
    strcpy(materias[11].nome, "Introdução à Probabilidade e à Estatística");
    materias[11].creditos = 3;
    strcpy(materias[12].nome, "Natureza da Informação");
    materias[12].creditos = 3;
    strcpy(materias[13].nome, "Processamento da Informação");
    materias[13].creditos = 5;
    strcpy(materias[14].nome, "Comunicação e Redes");
    materias[14].creditos = 3;
    strcpy(materias[15].nome, "Estrutura da Matéria");
    materias[15].creditos = 3;
    strcpy(materias[16].nome, "Física Quântica ");
    materias[16].creditos = 3;
    strcpy(materias[17].nome, "Interações Atômicas e Moleculares");
    materias[17].creditos = 3;
    strcpy(materias[18].nome, "Bioquímica: estrutura, propriedade e funções de biomoléculas");
    materias[18].creditos = 5;
    strcpy(materias[19].nome, "Bases Epistemológicas da Ciência Moderna");
    materias[19].creditos = 3;
    strcpy(materias[20].nome, "Estrutura e Dinâmica Social");
    materias[20].creditos = 3;
    strcpy(materias[21].nome, "Ciência, Tecnologia e Sociedade");
    materias[21].creditos = 3;
    strcpy(materias[22].nome, "Base Experimental das Ciências Naturais");
    materias[22].creditos = 3;
    strcpy(materias[23].nome, "Projeto Dirigido");
    materias[23].creditos = 2;
    strcpy(materias[24].nome, "Bases Computacionais da Ciência");
    materias[24].creditos = 2;
    strcpy(materias[25].nome, "Bases Matemáticas");
    materias[25].creditos = 4;
    strcpy(materias[26].nome, "Estado e Relações de Poder");
    materias[26].creditos = 4;
    strcpy(materias[27].nome, "Estrutura e Dinâmica Social");
    materias[27].creditos = 3;
    strcpy(materias[28].nome, "Introdução à economia");
    materias[28].creditos = 3;
    strcpy(materias[29].nome, "Introdução ao Pensamento Econômico");
    materias[29].creditos = 3;
    strcpy(materias[30].nome, "Ética e Justiça");
    materias[30].creditos = 4;
    strcpy(materias[31].nome, "Pensamento crítico");
    materias[31].creditos = 4;
    strcpy(materias[32].nome, "Temas e Problemas em Filosofia");
    materias[32].creditos = 3;
    strcpy(materias[33].nome, "Estudos de Gênero");
    materias[33].creditos = 3;
    strcpy(materias[34].nome, "Estudos Étnico-Raciais");
    materias[34].creditos = 3;
    strcpy(materias[35].nome, "Formação do Sistema Internacional");
    materias[35].creditos = 4;
    strcpy(materias[36].nome, "Identidade e Cultura");
    materias[36].creditos = 3;
    strcpy(materias[37].nome, "Interpretações do Brasil");
    materias[37].creditos = 4;
    strcpy(materias[38].nome, "Território e Sociedade");
    materias[38].creditos = 4;
    strcpy(materias[39].nome, "Ciência, Tecnologia e Sociedade");
    materias[39].creditos = 3;
    strcpy(materias[40].nome, "Desenvolvimento e Sustentabilidade");
    materias[40].creditos = 4;
    strcpy(materias[41].nome, "Bases Epistemológicas da Ciência Moderna");
    materias[41].creditos = 3;
    strcpy(materias[42].nome, "Introdução às Humanidades e às Ciências Sociais");
    materias[42].creditos = 2;
    strcpy(materias[43].nome, "Práticas em Ciências e Humanidades");
    materias[43].creditos = 3;
    strcpy(materias[44].nome, "Biodiversidade: Interações entre organismos e ambiente");
    materias[44].creditos = 3;
    strcpy(materias[45].nome, "Bases Computacionais da Ciência");
    materias[45].creditos = 2;
    strcpy(materias[46].nome, "Bases Matemáticas");
    materias[46].creditos = 4;
    strcpy(materias[47].nome, "Introdução à Probabilidade e à Estatística");
    materias[47].creditos = 3;


    ////Varíaveis utilizadas
    char nome[50];
    int buscarRA, result, posAluno = 0, i = 0, opcao2, area, entrada, opcao;
    float CR = 0;


    ///SOLICITANDO CRIAÇÃO DA LISTA
    RAs *alunoRA;
    alunoRA = criar_Lista();
    //**//////////

    historicoAlunos historico[w]; ////Declarando struct que armazena histórico


    do {
        int controleRAExiste = 0; //// Verifica se foi achado ou criado algum RA no menu abaixo e não ir para o próximo, caso negativo

        printf("\n[1]: Adicionar RA | [2]: Consultar RA | [0]: Sair\n");
        scanf("%d", &opcao);

        if (opcao == 1 || opcao == 2) {
            if (opcao == 1) { /////Opção adicionar RA
                printf("\nQual RA deseja cadastrar?\n");
                scanf("%d", &buscarRA);
                result = procuraRA(alunoRA, buscarRA);

                if (result == -2) {
                    printf("\nLista com erro.\n");
                } else if (result == -1) {
                    int j = adicionaRA(alunoRA, buscarRA);
                    if (j == -2) {
                        printf("\nErro ao cadastrar RA.");
                    } else if (j == -1) {
                        printf("\nLista cheia.");
                    } else {
                        historico[i].codigoMat[0] = 0;
                        posAluno = i++;
                        printf("Novo RA cadastrado com sucesso!\n");
                    }
                } else {
                    printf("\nRA já cadastrado!\n");
                    posAluno = result;
                }
            } else if (opcao == 2) { /////Opção consultar RA
                printf("\nQual RA deseja consultar?\n");
                scanf("%d", &buscarRA);
                result = procuraRA(alunoRA, buscarRA);

                if (result == -2) {
                    printf("\nLista com erro.\n");
                } else if (result == -1) {
                    printf("\nRA não encontrado\n.");

                    controleRAExiste++;
                } else {
                    printf("\nRA encontrado.\n");
                    posAluno = result;
                }
            }

            if (controleRAExiste == 0) {
                do {
                    printf("\nEscolha seu curso:\n[1] Bacharelado em Ciência e Tecnologia | [2] Bacharelado em Ciências e Humanidades | [0]Encerrar\n");
                    scanf("%d", &entrada);



                    if (entrada == 1) { ///////BC&T
                        do {
                            printf("\nEscolha a Sub-área:\n[1] Energia \n[2] Processos de Transformação \n[3] Representação e Simulação \n[4] Informação e Comunicação \n[5] Estrutura da Matéria \n[6] Humanidades \n[7] Inter-eixos \n[8] Grade  |  [0] Voltar \n");
                            scanf("%d", &area);
                            if (area < 0 || area > 8) {
                                printf("\nCódigo inválido. Digite novamente:\n");
                                scanf("%d", &area);
                            }
                        } while (area < 0 || area > 8);
                        materiasBI(area);
                    } else if (entrada == 2) { /////BC&H
                        do {
                            printf("\nEscolha a Sub-área:\n[9] Estado, Sociedade e Mercado \n[10] Pensamento, Expressão e Significado \n[11] Espaço, Cultura e Temporalidade \n[12] Ciência, Tecnologia e Inovação \n[13] Epistemologia e Metodologia \n[14] Ciências Naturais e Formais \n[15] Grade  |  [0] Voltar \n");
                            scanf("%d", &area);
                            if (area < 0 || area > 15) {
                                printf("\nCódigo inválido. Digite novamente:\n");
                                scanf("%d", &area);
                            }
                        } while (area < 0 || area > 15);
                        materiasBI(area);
                    } else if (entrada != 0) { //////Código inválido
                        printf("\nCódigo inválido. Digite novamente:\n");
                        scanf("%d", &entrada);
                    }

                    do {

                        if (historico[posAluno].codigoMat[0] == 0 && entrada != 0) { ////Caso aluno não possua matérias cadastradas
                            printf("\n[1]: Adicionar Matéria | [0]: Sair\n");
                            scanf("%d", &opcao2);
                            if (opcao2 != 0) {
                                encontraOpcao(historico, posAluno, opcao2);

                            }
                        } else if (historico[posAluno].codigoMat[0] > 0 && entrada != 0) { //////Caso o aluno já possua matérias cadastradas
                            printf("\n[1]: Adicionar Matéria | [2]: Remover Matéria | [3]: Listar matérias cursadas \n            [4]: Calcular CR | [0]: Sair\n");
                            scanf("%d", &opcao2);
                            encontraOpcao(historico, posAluno, opcao2);
                        }
                    } while (opcao2 != 0);
                } while (entrada != 0);
            }
        }

    } while (opcao != 0);
}

void adcMateria(historicoAlunos *historico, int posAluno) ////Adiciona materia no RA
{
    int codMateria;
    int y = historico[posAluno].codigoMat[0]; /////Qntd de mantérias já cadastradas
    int x = y + 1; /////x é a posição onde deverá ser acrescentada a matéria


    do {
        printf("\nDigite o código da matéria para adicionar ou -1 para voltar:\n");
        scanf("\n%d", &codMateria);
        codMateria--;
        if (codMateria != -2) {
            if (codMateria < 46) {
                historico[posAluno].codigoMat[x] = codMateria;
                char carac;
                do {
                    printf("Digite o conceito:\n");
                    scanf(" %c", &carac);
                    if (carac != 'a' && carac != 'b' && carac != 'c' && carac != 'd' && carac != 'f' && carac != 'o'
                            && carac != 'A' && carac != 'B' && carac != 'C' && carac != 'D' && carac != 'F' && carac != 'O') {

                        printf("Conceito incorreto, digite novamente:\n");
                        scanf("%c", &carac);
                    }
                } while (carac != 'a' && carac != 'b' && carac != 'c' && carac != 'd' && carac != 'f' && carac != 'o'
                        && carac != 'A' && carac != 'B' && carac != 'C' && carac != 'D' && carac != 'F' && carac != 'O');

                historico[posAluno].nota[x++] = toupper(carac); ////Padroniza em letra maiúscula

                historico[posAluno].codigoMat[0] += 1;
            } else {
                printf("Matéria não encontrada.\n");
            }
        }
    } while (codMateria != -2);
}

void delMateria(historicoAlunos *historico, int posAluno) ////Deleta materias ja cadastradas
{
    int n, m, g;
    int qntdMatCursadas = historico[posAluno].codigoMat[0];

    for (n = 1; n <= qntdMatCursadas; n++) {
        char carac = historico[posAluno].nota[n];
        printf("%d - %s - Nota: %c\n", n, materias[historico[posAluno].codigoMat[n]].nome, carac);
    }

    do {
        printf("\nDigite a posição em que se encontra a matéria que deseja excluir ou -1 para cancelar entrada:\n");
        scanf("\n%d", &n);
        m = n;
        g = n;
        printf("%d", qntdMatCursadas);

        if (n > 0 && n <= qntdMatCursadas) {
            while (m <= historico[posAluno].codigoMat[0]) {
                if (m < (historico[posAluno].codigoMat[0])) {
                    int p = m + 1;
                    int j = historico[posAluno].codigoMat[p]; /////////// j = codMateria[m+1]
                    int k = historico[posAluno].nota[p]; /////////// k = nota[m+1]
                    historico[posAluno].codigoMat[m] = j; //////////Faz a substituição da posição anterior (m) pela posterior (m+1)
                    historico[posAluno].nota[m] = k;
                } else {
                    historico[posAluno].codigoMat[m] = 0; ////Na última posíção antes cadastrada, é zerado
                    historico[posAluno].nota[m] = 0;
                }
                m++;
            }

            n--;
            qntdMatCursadas--; ////Diminui a qntd de matérias cursadas
            historico[posAluno].codigoMat[0] = qntdMatCursadas;
            printf("Remoção feita com sucesso.\n");
        } else if (n > qntdMatCursadas || g == 0 || g < -1) {
            printf("\nCódigo inválido.\n");
        }
    } while (n > qntdMatCursadas || g == 0 || g < -1);

}

void listarMaterias(historicoAlunos *historico, int posAluno) {
    printf("\n");
    if (historico[posAluno].codigoMat[0] != 0) {
        for (int i = 1; i <= historico[posAluno].codigoMat[0]; i++) {
            char caraca = historico[posAluno].nota[i];
            printf("%s - Conceito: %c\n", materias[historico[posAluno].codigoMat[i]].nome, caraca);
        }
    } else {
        printf("\nNenhuma matéria cadastrada.");
    }
}

void calculCR(historicoAlunos *historico, int posAluno)//calcular CR
{
    int acum = 0, soma = 0;
    double alunoCR = 0;

    for (int i = 1; i <= historico[posAluno].codigoMat[0]; i++) {
        switch (historico[posAluno].nota[i]) {
            case 'A':
                acum = acum + 4 * materias[historico[posAluno].codigoMat[i]].creditos;
                break;
            case 'B':
                acum = acum + 3 * materias[historico[posAluno].codigoMat[i]].creditos;
                break;
            case 'C':
                acum = acum + 2 * materias[historico[posAluno].codigoMat[i]].creditos;
                break;
            case 'D':
                acum = acum + 1 * materias[historico[posAluno].codigoMat[i]].creditos;
                break;
            default:
                acum = acum + 0 * materias[historico[posAluno].codigoMat[i]].creditos;
        }

        soma = soma + materias[(historico[posAluno].codigoMat[i])].creditos;

        alunoCR = (double) acum / soma;
    }
    printf("\n");
    printf("\nSeu CR é: %.2f\n", alunoCR);
}

void encontraOpcao(historicoAlunos *historico, int posAluno, int opcao) {
    if (opcao == 1) {
        adcMateria(historico, posAluno);
    } else if (opcao == 2) {
        delMateria(historico, posAluno);
    } else if (opcao == 3) {
        listarMaterias(historico, posAluno);
    } else if (opcao == 4) {
        calculCR(historico, posAluno);
    }
}

void materiasBI(int opcao) {
    int i = 0;

    if (opcao == 1) {
        printf("\nVocê escolheu a categoria: Energia \n");
        for (i = 0; i < 4; i++) {
            printf("[%d] %s | Qtd créditos: %d\n", i + 1, materias[i].nome, materias[i].creditos);
        }
    } else if (opcao == 2) {
        printf("\nVocê escolheu a categoria: Processos de Transformação \n");
        for (int i = 4; i < 7; i++) {
            printf("[%d] %s | Qtd créditos: %d\n", i + 1, materias[i].nome, materias[i].creditos);
        }

    } else if (opcao == 3) {
        printf("\nVocê escolheu a categoria: Representação e Simulação \n");
        for (int i = 7; i < 12; i++) {
            printf("[%d] %s | Qtd créditos: %d\n", i + 1, materias[i].nome, materias[i].creditos);
        }
    } else if (opcao == 4) {
        printf("\nVocê escolheu a categoria: Informação e Comunicação \n");
        for (int i = 12; i < 15; i++) {
            printf("[%d] %s | Qtd créditos: %d\n", i + 1, materias[i].nome, materias[i].creditos);
        }
    } else if (opcao == 5) {
        printf("\nVocê escolheu a categoria: Estrutura da Matéria \n");
        for (int i = 15; i < 19; i++) {
            printf("[%d] %s | Qtd créditos: %d\n", i + 1, materias[i].nome, materias[i].creditos);
        }
    } else if (opcao == 6) {
        printf("\nVocê escolheu a categoria: Humanidades \n");
        for (int i = 19; i < 22; i++) {
            printf("[%d] %s | Qtd créditos: %d\n", i + 1, materias[i].nome, materias[i].creditos);
        }
    } else if (opcao == 7) {
        printf("\nVocê escolheu a categoria: Inter-eixos \n");
        for (int i = 22; i < 26; i++) {
            printf("[%d] %s | Qtd créditos: %d\n", i + 1, materias[i].nome, materias[i].creditos);
        }
    } else if (opcao == 9) {
        printf("\nVocê escolheu a categoria: Estado, Sociedade e Mercado \n");
        for (i = 26; i < 30; i++) {
            printf("[%d] %s | Qtd créditos: %d\n", i + 1, materias[i].nome, materias[i].creditos);
        }
    } else if (opcao == 10) {
        printf("\nVocê escolheu a categoria: Pensamento, Expressão e Significado \n");
        for (i = 30; i < 33; i++) {
            printf("[%d] %s | Qtd créditos: %d\n", i + 1, materias[i].nome, materias[i].creditos);
        }
    } else if (opcao == 11) {
        printf("\nVocê escolheu a categoria: Espaço, Cultura e Temporalidade \n");
        for (i = 33; i < 39; i++) {
            printf("[%d] %s | Qtd créditos: %d\n", i + 1, materias[i].nome, materias[i].creditos);
        }
    } else if (opcao == 12) {
        printf("\nVocê escolheu a categoria: Ciência, Tecnologia e Inovação \n");
        for (i = 39; i < 41; i++) {
            printf("[%d] %s | Qtd créditos: %d\n", i + 1, materias[i].nome, materias[i].creditos);
        }
    } else if (opcao == 13) {
        printf("\nVocê escolheu a categoria: Epistemologia e Metodologia \n");
        for (i = 41; i < 44; i++) {
            printf("[%d] %s | Qtd créditos: %d\n", i + 1, materias[i].nome, materias[i].creditos);
        }
    } else if (opcao == 14) {
        printf("\nVocê escolheu a categoria: Ciências Naturais e Formais \n");
        for (int i = 44; i < 48; i++) {
            printf("[%d] %s | Qtd créditos: %d\n", i + 1, materias[i].nome, materias[i].creditos);
        }
    }
}
