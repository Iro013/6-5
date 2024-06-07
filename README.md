# 스택, 큐, 백터, 연결리스트 구현


스택
```
#include <stdio.h>

int stack[100];
int top=-1;
int push(int n);
int pop();


int main() {
	int count,n,i,j;
	scanf("%d",&count);

	for(int i=0;i<count;i++){
		printf("push:0 or pop:1  :");
		scanf("%d",&j);
		if(j==0){
			scanf("%d",&n);
			push(n);
		}
		else
			pop();

		
	}
	return 0;
}

int push(int n){
	if(top==99){
		printf("stack is full\n");
	}
	else{
		top++;
		stack[top]=n;
	}
	return 0;
}

int pop(){
	if(top==-1){
		printf("stack is empty\n");
	}
	else{
		printf("%d",stack[top]);
		top--;
	}
	return 0;
}
```

큐
```
#include <stdio.h>

int queue[100];
int back=-1;
int push(int n);
int pop();


int main() {
	int count,n,i,j;
    printf("How many times to run? : ");
	scanf("%d",&count);

	for(int i=0;i<count;i++){
		printf("%d. push:0 or pop:1  :",i+1);
		scanf("%d",&j);
		if(j==0){
			scanf("%d",&n);
			push(n);
		}
		else
			pop();

		
	}
    for(int i=0;i<back;i++){
        printf("%d ", queue[i]);

    }
    return 0;
}

int push(int n){
    if(back==99)
        printf("queue is full\n");
    else{
        back++;
        queue[back]=n;
    }
    return 0;
}

int pop(){
    if(back<0){
        printf("queue is empty\n");
    }
    else{
        printf("%d\n",queue[0]);
        for (int i = 0; i < back; i++)
		    queue[i - 1] = queue[i];
        back--;
    }
}
```

연결리스트
```
#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node *next;
};

int main() {
    struct Node *head = NULL;
    head = (struct Node*) malloc(sizeof(struct Node));
    head->data = 1;
    head->next = NULL;
    return 0;
}
```
STL Vector
```
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

void init(struct Vector *vec);
void puch(struct Vector *vec, int num);
void pop(struct Vector *vec);
void resize(struct Vector *vec, size_t new_count);

struct Vector{
    int *data;
    size_t size;
    size_t count;
};

int main(){
    
    return 0;
}


void init(struct Vector *vec){
    vec->size=0;
    vec->count= 4;
    vec-> data =(int *)malloc(vec->count * sizeof(int));
}

void resize(struct Vector *vec, size_t new_count) {
    vec->count = new_count;
    vec->data = (int *)realloc(vec->data, vec->count* sizeof(int));
}

void puch(struct Vector *vec, int num){
    if (vec->size >= vec->count) {
        resize(vec, vec->count * 2);
    }
    vec->data[vec->size++] = num;
}

void pop(struct Vector *vec) {
    if (vec->size > 0) {
        vec->size--;
    } else {
        printf("Vector is empty\n");
    }
}
```
