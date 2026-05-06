#include <stdio.h>
#include <stdlib.h>

int gerar_id(char nome_arquivo[]) {
    FILE *arq = fopen(nome_arquivo, "r");
    int id = 1;
    char linha[200];

    if (arq != NULL) {
        while (fgets(linha, sizeof(linha), arq)) {
            id++;
        }
        fclose(arq);
    }

    return id;
}

int main() {
    int opcao;

    printf("1 - Cadastrar Aluno\n");
    printf("2 - Cadastrar Professor\n");
    printf("3 - Cadastrar Disciplina\n");
    printf("4 - Realizar Matricula\n");
    printf("Escolha: ");
    scanf("%d", &opcao);

    // ================= ALUNO =================
    if (opcao == 1) {
        int id = gerar_id("alunos.txt");
        char nome[50], turma[20];

        printf("Nome: ");
        scanf("%s", nome);

        printf("Turma: ");
        scanf("%s", turma);

        FILE *arq = fopen("alunos.txt", "a");
        FILE *banco = fopen("banco.txt", "a");

        fprintf(arq, "%d %s %s\n", id, nome, turma);
        fprintf(banco, "ALUNO %d %s %s\n", id, nome, turma);

        fclose(arq);
        fclose(banco);

        printf("Aluno cadastrado!\n");
    }

    // ================= PROFESSOR =================
    else if (opcao == 2) {
        int id = gerar_id("professores.txt");
        char nome[50], area[50];

        printf("Nome: ");
        scanf("%s", nome);

        printf("Area: ");
        scanf("%s", area);

        FILE *arq = fopen("professores.txt", "a");
        FILE *banco = fopen("banco.txt", "a");

        fprintf(arq, "%d %s %s\n", id, nome, area);
        fprintf(banco, "PROF %d %s %s\n", id, nome, area);

        fclose(arq);
        fclose(banco);

        printf("Professor cadastrado!\n");
    }

    // ================= DISCIPLINA =================
    else if (opcao == 3) {
        int id = gerar_id("disciplinas.txt");
        int id_prof, ch;
        char nome[50];

        printf("Nome da disciplina: ");
        scanf("%s", nome);

        printf("ID do professor: ");
        scanf("%d", &id_prof);

        printf("Carga horaria: ");
        scanf("%d", &ch);

        FILE *arq = fopen("disciplinas.txt", "a");
        FILE *banco = fopen("banco.txt", "a");

        fprintf(arq, "%d %s %d %d\n", id, nome, id_prof, ch);
        fprintf(banco, "DISC %d %s %d %d\n", id, nome, id_prof, ch);

        fclose(arq);
        fclose(banco);

        printf("Disciplina cadastrada!\n");
    }

    // ================= MATRICULA =================
    else if (opcao == 4) {
        int id_disc, id_aluno;
        char periodo[20];

        printf("ID da disciplina: ");
        scanf("%d", &id_disc);

        printf("ID do aluno: ");
        scanf("%d", &id_aluno);

        printf("Periodo: ");
        scanf("%s", periodo);

        FILE *arq = fopen("matriculas.txt", "a");
        FILE *banco = fopen("banco.txt", "a");

        fprintf(arq, "%d %d %s\n", id_disc, id_aluno, periodo);
        fprintf(banco, "MAT %d %d %s\n", id_disc, id_aluno, periodo);

        fclose(arq);
        fclose(banco);

        printf("Matricula realizada!\n");
    }

    else {
        printf("Opcao invalida!\n");
    }

    return 0;
}
