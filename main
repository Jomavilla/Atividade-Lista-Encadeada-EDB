#include <stdio.h>
#include <stdlib.h>

typedef struct no {
   int info;
   struct no *prox;
}Lista;

Lista* crialista() {
    return NULL;
}

Lista* insere(Lista *list, int valor) {
    Lista *novo = (Lista*) malloc(sizeof(Lista));
    novo->info = valor;
    novo->prox = list;
    return novo;
}

void imprime (Lista *list) {
    Lista *p;
    for (p = list; p != NULL; p = p->prox) {
        printf("info = %d\n", p->info);
    }
}

int estavazia(Lista *list) {
    return (list == NULL);
}

Lista* busca (Lista *list, int valor) {
    Lista *p;
    for (p = list; p != NULL ; p = p->prox){
      if(p->info == valor){
        printf("O valor %d foi encontrado com sucesso !!\n",valor);
        return p;
      }
    } 
    printf("ERRO!!! : Valor não encontrado\n");
    return NULL;         
}

Lista *retira(Lista *lista, int v) {
        Lista *ant = NULL;
        Lista *p = lista;

        while (p != NULL && p->info != v) {
            ant = p;
            p = p->prox;
        }

        if (p==NULL) {
            return lista;
        }

        if (ant==NULL) {
                lista = p->prox;
        } else {
            ant->prox = p->prox;
        }
	free(p);
	return lista;
}

Lista* libera(Lista* lista){
  Lista *p;
   while(p != NULL){
    p = lista->prox;
    free(lista);
    lista = p;
  }
  return NULL;
}

int main(){
  Lista* minhalista;

  minhalista = crialista();

  minhalista = insere(minhalista, 88);
  minhalista = insere(minhalista, 71);
  minhalista = insere(minhalista, 23);
  minhalista = insere(minhalista, 12);
  minhalista = insere(minhalista, 29);
  minhalista = insere(minhalista, 1);

  imprime(minhalista);

  busca(minhalista, 70);
  busca(minhalista, 29);

  minhalista = retira(minhalista, 12);
  minhalista = retira(minhalista, 23);
  minhalista = retira(minhalista, 1);

  imprime(minhalista);

  libera(minhalista);


  return 0;
}
