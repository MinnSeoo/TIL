## Stack
```
#include <stdio.h>
#include <stdlib.h>

typedef struct _node {
	int data;
	struct _node* next;
}Node;

Node *top = NULL;

// 연결리스트 기반 스택
void push(int data) {
	Node *newNode = (Node*)malloc(sizeof(Node));
	newNode->data = data;
	newNode->next = NULL;

	if (top == NULL)
		top = newNode;

	else {	// 2. n-> n +1
		newNode->next = top;
		top = newNode;
	}

	// if (top != NULL) 
	//	newNode->next = top;
	//top = newNode;
}

int pop() {
	if (top != NULL) {
		Node* delNode;
		delNode = top;
		top = top->next;

		int tmp = delNode->data;
		free(delNode);
		return tmp;
	}
	else {
		printf("꺼낼 데이터가 없는데 pop을 요청(강제종료)\n");
		exit(1118);
	}
}

// top이 null을 가리키도록 하게함.
void init() {
	if (top != NULL) {
		while (top != NULL) {
			Node* delNode = top;
			top = top->next;
			free(delNode);
		}
	}
}

int peek() {
	if (top != NULL)
		return top->data;

	else {
		printf("확인할 데이터가 없는데 peek를 요청(강제종료)\n");
		exit(1105);
	}
}

int main() {
	init();
	push(10), push(20);
	printf("pop() : %d\n", pop());
	printf("pop() : %d\n", pop());
	printf("peek() : %d\n", peek());
	

}
```