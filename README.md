# Trabalho_super_trunfo
#include <stdio.h>

// Estrutura para armazenar as informações de cada cidade
typedef struct {
    char estado[50];
    int codigo;
    char nome[100];
    int populacao;
    float pib;
    float area;
    int pontosTuristicos;
    float densidadePopulacional;
    float pibPerCapita;
} Cidade;

// Função para calcular a densidade populacional
float calcularDensidade(int populacao, float area) {
    return populacao / area;
}

// Função para calcular o PIB per capita
float calcularPIBPerCapita(float pib, int populacao) {
    return pib / populacao;
}

// Função para registrar uma cidade
void registrarCidade(Cidade *c) {
    printf("\n--- Cadastro de Cidade ---\n");

    printf("Digite o nome da cidade: ");
    scanf(" %[^\n]", c->nome);

    printf("Digite o estado: ");
    scanf(" %[^\n]", c->estado);

    printf("Digite o código da cidade: ");
    scanf("%d", &c->codigo);

    printf("Digite a população: ");
    scanf("%d", &c->populacao);

    printf("Digite o PIB (em milhões): ");
    scanf("%f", &c->pib);

    printf("Digite a área (em km²): ");
    scanf("%f", &c->area);

    printf("Digite o número de pontos turísticos: ");
    scanf("%d", &c->pontosTuristicos);

    // Cálculos derivados
    c->densidadePopulacional = calcularDensidade(c->populacao, c->area);
    c->pibPerCapita = calcularPIBPerCapita(c->pib, c->populacao);
}

// Função para exibir os dados de uma cidade
void exibirCidade(Cidade c) {
    printf("\n--- Carta da Cidade ---\n");
    printf("Nome: %s\n", c.nome);
    printf("Estado: %s\n", c.estado);
    printf("Código: %d\n", c.codigo);
    printf("População: %d habitantes\n", c.populacao);
    printf("PIB: R$ %.2f milhões\n", c.pib);
    printf("Área: %.2f km²\n", c.area);
    printf("Pontos turísticos: %d\n", c.pontosTuristicos);
    printf("Densidade populacional: %.2f hab/km²\n", c.densidadePopulacional);
    printf("PIB per capita: R$ %.2f\n", c.pibPerCapita);
}

int main() {
    Cidade cidade;

    registrarCidade(&cidade);
    exibirCidade(cidade);

    return 0;
}
