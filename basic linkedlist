#include <stdio.h>
#include <stdlib.h>
#include <string.h>

struct Node {
	int data;
	struct Node *next;

};

struct LinkedList {
	struct Node *head;
	int size;
};

void add_nodes(struct LinkedList* list);

void print_reversed(struct Node* tmp);

void print_nodes(struct LinkedList* list);

void add_first(struct LinkedList* list);

void add_last(struct LinkedList* list);

void add_in_middle(struct LinkedList* list);

void delete_node(struct LinkedList* list);

int main(void) {

	struct LinkedList* list = malloc(sizeof(struct LinkedList));
	list->head = malloc(sizeof(struct Node));

	while (1) {
	
		char *command;
		fgets(command, 20, stdin);
		command[strlen(command) - 1] = '\0';

		if (strcmp(command, "create") == 0) {
			int n;
			scanf("%d", &n);
			list->size = n;
			add_nodes(list);
		}
		else if (strcmp(command, "first") == 0) {
			add_first(list);
		}
		else if (strcmp(command, "last") == 0) {
			add_last(list);
		}
		else if (strcmp(command, "middle") == 0) {
			add_in_middle(list);
		}
		else if (strcmp(command, "print") == 0) {
			print_nodes(list);
		}
		else if (strcmp(command, "reverse") == 0) {
			printf("Reversed nodes' data:\n");
			print_reversed(list->head);
		}
		else if (strcmp(command, "delete node") == 0) {
			delete_node(list);
		}
		else if (strcmp(command, "exit") == 0) {
			break;
		}
	}

	return 0;
}

void delete_node(struct LinkedList* list) {

	printf("Which node to delete (give index)?:\n");

	int del_index, index = 0;
	scanf("%d", &del_index);
	if (del_index >= list->size || del_index < 0) {
		printf("Please give a valid index\n");
		return;
	}
	
	struct Node* tmp;
	tmp = list->head;

	if (del_index == 0) {
		list->head = tmp->next;
		return;
	}

	while (index < del_index - 1) {
		tmp = tmp->next;
		index++;
	}

	list->size--;
	tmp->next = tmp->next->next;
}

void add_in_middle(struct LinkedList* list) {

	printf("What node to add in the middle?:\n");

	struct Node* tmp, *newptr;
	tmp = list->head;
	int index = 0;

	while (tmp != NULL)
		tmp = tmp->next;

	tmp = malloc(sizeof(struct Node));
	scanf("%d", &tmp->data);

	newptr = list->head;

	while (index < list->size / 2 - 1) {
		newptr = newptr->next;
		index++;
	}

	tmp->next = newptr->next;
	newptr->next = tmp;
}

void add_last(struct LinkedList* list) {

	printf("What node to add last?:\n");

	struct Node* tmp;
	tmp = list->head;

	while (tmp->next != NULL)
		tmp = tmp->next;

	tmp->next = malloc(sizeof(struct Node));
	list->size++;

	scanf("%d", &tmp->next->data);
}

void add_first(struct LinkedList* list) {

	printf("What node to add first?:\n");

	struct Node* tmp;
	tmp = list->head;

	while (tmp != NULL)
		tmp = tmp->next;

	tmp = malloc(sizeof(struct Node));
	list->size++;

	tmp->next = list->head;
	list->head = tmp;

	scanf("%d", &tmp->data);
}

void add_nodes(struct LinkedList* list) {

	struct Node* tmp = malloc(sizeof(struct Node));
	int index = 0;

	tmp = list->head;

	while (index < list->size) {

		scanf("%d", &tmp->data);

		if (index < list->size - 1) {
			tmp->next = malloc(sizeof(struct Node));
			tmp = tmp->next;
		}
		index++;
	}
}

void print_nodes(struct LinkedList* list) {

	struct Node* tmp = malloc(sizeof(struct Node));

	tmp = list->head;

	printf("The nodes' datas are:\n");

	while (tmp != NULL) {

		printf("%d\n", tmp->data);
		tmp = tmp->next;
	}
}

void print_reversed(struct Node* tmp) {

	if (tmp == NULL)
		return;

	print_reversed(tmp->next);
	printf("%d\n", tmp->data);
}
