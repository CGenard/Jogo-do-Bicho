# Jogo-do-Bicho
Jogo do Bicho made in Phyton.

#include <stdio.h>
#include <stdlib.h>
#include <stdbool.h>
#include <string.h>
#include <time.h>

#define NUM_ANIMALS 25
#define NUM_NUMEROS 4
#define MAX_BETS 100

const char* animals[NUM_ANIMALS] = {
 "Ostrich", "Eagle", "Donkey", "Butterfly", "Dog",
 "Goat", "Sheep", "Camel", "Snake", "Rabbit",
 "Horse", "Elephant", "Rooster", "Cat", "Alligator",
 "Lion", "Monkey", "Pig", "Peacock", "Turkey",
 "Bull", "Tiger", "Bear", "Deer", "Cow"
};


int numbers[NUM_ANIMALS][NUM_NUMEROS] = {
 {1, 2, 3, 4}, {5, 6, 7, 8}, {9, 10, 11, 12}, {13, 14, 15, 16},
 {17, 18, 19, 20}, {21, 22, 23, 24}, {25, 26, 27, 28}, {29, 30, 31, 32},
 {33, 34, 35, 36}, {37, 38, 39, 40}, {41, 42, 43, 44}, {45, 46, 47, 48},
 {49, 50, 51, 52}, {53, 54, 55, 56}, {57, 58, 59, 60}, {61, 62, 63, 64},
 {65, 66, 67, 68}, {69, 70, 71, 72}, {73, 74, 75, 76}, {77, 78, 79, 80},
 {81, 82, 83, 84}, {85, 86, 87, 88}, {89, 90, 91, 92}, {93, 94, 95, 96},
 {97, 98, 99, 100}
};

bool check_bet(const char* animal_bet, int bet_number) {
 for (int i = 0; i < NUM_ANIMALS; i++) {
 if (strcmp(animals[i], animal_bet) == 0) {
 for (int j = 0; j < NUM_NUMEROS; j++) {
 if (numbers[i][j] == bet_number) {
 return true;
 }
 }
 }
 }
 return false;
}
int perform_sorteio() {
 return rand() % 100 + 1;
}

int main() {
 srand(time(NULL));
 char animal_bet[MAX_BETS][20];
 int bet_number[MAX_BETS];
 int total_bets = 0;
 int winning_bets = 0;
 char option;

 of {

 printf("Enter the name of the animal for your bet: ");
 scanf("%s", animal_bet[total_bets]);
 printf("Enter the number associated with your bet: ");
 scanf("%d", &number_bet[total_bets]);

 total_bets++;
 printf("Do you want to place another bet? (y/n): ");
 scanf(" %c", &opcao);
 } while ((option == 's' || option == 'S') && total_bets < MAX_BETS);

 int number_sorted = perform_sorteio();
 printf("Number drawn: %d\n", number_drawn);

 for (int i = 0; i < total_bets; i++) {
 if (check_bet(animal_bet[i], drawn_number)) {
 printf("Congratulations! Your bet on animal %s with the number %d was a winner!\n", animal_bet[i], drawn_number);
 winning_bets++;
 } else {
 printf("What a shame! Your bet on animal %s with the number %d was not a winner.\n", animal_bet[i], number_sorted);
 }
 }
 printf("Total bets: %d\n", total_bets);
 printf("Winning bets: %d\n", winning_bets);

 return 0;
}
