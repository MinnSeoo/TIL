## **STACK**
```
#include <stdio.h>
#include <stdlib.h>

typedef struct _node {
	int data;
	struct _node* next;
}Node;

Node *top = NULL;

<연결리스트 기반 스택>
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

     <데이터 삽입 (위의 코드를 간략히 작성하고 싶을 시 !!)>
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
		exit(1118);     // exit = 강제종료
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

```
<배열기반 스택>
#define STACK_SIZE 10

  int topIdx = -1;		// -1 == 데이터가 존재하지 않을때
  int arrayStack[STACK_SIZE];

    int stackInt() {    // 데이터 초기화
	    topIdx = -1;
    }

    void push(int data) {       // 데이터 삽입,추가
	if (topIdx < STACK_SIZE - 1) {
		arrayStack[++topIdx] = data;
	}
	

    }

    int pop() { // 데이터 삭제
	if (topIdx >= 0) {
		return arrayStack[topIdx--];
		/*int returnData = arrayStack[top];
		top--;
		return returnData;*/
	}
	
	exit(-1); // 오류코드 강제 종료후 -1 반환
}

    int peek() {    // 데이터 탐색
	if (topIdx >= 0) {
		return arrayStack[topIdx];
    }
}
