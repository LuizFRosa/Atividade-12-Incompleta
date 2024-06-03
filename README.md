# Atividade-12-Incompleta

#include <stdio.h>
#include <stdlib.h>
#include <Windows.h>
#include <locale.h>

// Declaração de funções
void menuPrincipal();
void digitarNotasAluno(float notas[][4], char nomes[][50], int* totalAlunos);
void mostrarNotasAlunos(float notas[][4], char nomes[][50], int totalAlunos);
void editarNotaAluno(float notas[][4], char nomes[][50], int totalAlunos);
void sairPrograma(char sair[][50]);

int main() {
	
	
	system("color F0");

	Sleep(500);

	printf("\nBem-vindo!\n\n");

	printf("Carregando o Progama... Aguarde um instante");

	Sleep(1000);

  // Variáveis para o menu e armazenamento de dados
  int opcao, totalAlunos = 0;
  float notas[5][4];  // Matriz para armazenar as notas dos alunos (5 linhas - alunos, 4 colunas - notas)
  char nomes[5][50];   // Matriz para armazenar os nomes dos alunos (5 linhas - alunos, 50 colunas - nome)

  do {
    menuPrincipal();
    printf("Digite sua opção: ");
    scanf("%d", &opcao);

    switch (opcao) {
      case 1:
        digitarNotasAluno(notas, nomes, &totalAlunos);
        break;
      case 2:
        mostrarNotasAlunos(notas, nomes, totalAlunos);
        break;
      case 3:
        editarNotaAluno(notas, nomes, totalAlunos);
        break;
      case 4:
        sairPrograma(sair);
        break;
      default:
        printf("\nOpção inválida. Tente novamente.\n");
    }
  } while (opcao != 4);

  return 0;
}

// Função para exibir o menu principal
void menuPrincipal() {
  system("cls"); // Limpa a tela
  printf("\nMENU\n");
  printf("1. Digitar notas dos alunos\n");
  printf("2. Mostrar notas dos alunos\n");
  printf("3. Editar nota de aluno\n");
  printf("4. Sair\n");
}

// Função para digitar as notas dos alunos
void digitarNotasAluno(float notas[][4], char nomes[][50], int* totalAlunos) {
  int i;

  system("cls"); // Limpa a tela

  if (*totalAlunos >= 5) {
    printf("\nNão é possível cadastrar mais alunos. Limite máximo de 5 alunos atingido.\n");
    system("pause");
    return;
  }

  printf("\nDigite os dados do aluno %d:\n", *totalAlunos + 1);

  printf("Nome: ");
  scanf("%s", nomes[*totalAlunos]);

  for (i = 0; i < 4; i++) {
    printf("Digite a nota %d: ", i + 1);
    scanf("%f", &notas[*totalAlunos][i]);
  }

  (*totalAlunos)++; // Incrementa o contador de alunos cadastrados
  system("pause");
}

// Função para mostrar as notas dos alunos
void mostrarNotasAlunos(float notas[][4], char nomes[][50], int totalAlunos) {
  int i, j;

  if (totalAlunos == 0) {
    printf("\nNenhum aluno cadastrado ainda.\n");
    system("pause");
    return;
  }

  system("cls"); // Limpa a tela
  printf("\nNotas dos Alunos:\n");

  for (i = 0; i < totalAlunos; i++) {
    printf("\nAluno: %s\n", nomes[i]);

    for (j = 0; j < 4; j++) {
      printf("Nota %d: %.2f\n", j + 1, notas[i][j]);
    }
  }

  system("pause");
}

// Função para editar nota de um aluno
void editarNotaAluno(float notas[][4], char nomes[][50], int totalAlunos) {
  int aluno, nota, novaNota;

  if (totalAlunos == 0) {
    printf("\nNenhum aluno cadastrado ainda.\n");
    system("pause");
    return;
  }

  system("cls"); // Limpa a tela
  printf("\nEditar nota de aluno\n");

  printf("Digite o número do aluno: ");
  scanf("%d", &aluno);

  if (aluno <= 0 || aluno > totalAlunos) {
}
system("pause");
}

// Função para sair do programa
void sairPrograma(char sair[][50]) {
system("cls");
        // Sair do menu
	Sleep(500);
        printf("\nSaindo do programa... Aguarde um pouco\n");
	Sleep(1000);
        break;

 return 0
}
