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

