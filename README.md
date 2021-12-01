
#include "hash.h"
#include <stdio.h>
#include <stdlib.h>
#include <string.h>


int main(int argc, char** argv) {
	int p = 10, numeroElementos = 0, i=0, aux2;
	char aux[150], *aux1;
	Chave vet1[p];
	FILE *fp;
	inicializaVetor(vet1, p);


	if((fp = fopen( "chaves2M.txt", "r")) == NULL ) {
		printf("Arquivo não encontrado\n");
		exit(1);
	}




	while(!feof(fp) && i<10){
		Chave novo;
		fgets(aux,150, fp);
		aux1 = strtok(aux, " ");
		aux2 = atoi(strtok(NULL, " "));
		novo.numero = aux2;	
		novo.string = (char*) malloc (150*sizeof(char));
		strcpy(novo.string,aux1);
		novo.prox = NULL;	
		insere(novo, p, vet1);


		i++;

	}
	imprimeVetor(10, vet1);









}
