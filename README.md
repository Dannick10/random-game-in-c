#include <stdio.h>
#include <time.h>
#include <stdbool.h>
#include <locale.h>

//Variaveis globais

int randp,rande;
 int ms = 1;
int player = 60;
int enemy = 60;
char string1[10];
char string2[10];


/*
*     Função para inserir o nome 
  */

int nome()
{
  printf("Digite o primeiro nome: ");
  fgets(string1,10,stdin);
  printf("Digite o segundo nome: ");
    fgets(string2,10,stdin);
}

/*
*     Função para geração de numero aleatorio jogador 1
  */

int  dadop()
{
  srand(time(NULL));
  randp = rand()%6+1;
    sleep(ms);
    printf("\n\n🎲⚪️| %i\n", randp);
}

/*
*     Função para geração de numero aleatorio jogador 2
  */

int  dadoe()
{
  srand(time(NULL));
  rande = rand()%6+1;
    sleep(ms);
  printf("\n\n🎲⚫️| %i\n", rande);
}

/*
* Vereficação dos numeros dos usario |maior ou menor que|
  */

int verefic()
{
if( randp >= rande)
{
 
    
  enemy = enemy - 10;
} if( rande >= randp){
       
    player = player - 10;
} 
  
 
}

/*
*    Saida do 2 usuario
  */

int enemys()
{

    printf("\n---------------------------\n");

   printf("\n⚫️ %s \n",string1);
  printf("_____________");
   Lifebarrae();
     printf("\n---------------------------\n");
}

/*
*    Saida do 1 usuario
  */


int players()
{
  
     printf("\n---------------------------\n");

  printf("\n⚪️ %s \n",string2);
   printf("_____________");
    Lifebarrap();
   
}

/*
*    Barra de life do 1 usuario
  */


int Lifebarrap()
{
  
 if(player == 50)
 {
   printf("\n❤ ██████ 50%");
 }

  if(player == 40)
 {
   printf("\n❤ █████░ 40%");
 }

   if(player == 30)
 {
   printf("\n❤ ████░░ 30%");
 }

   if(player == 20)
 {
   printf("\n❤ ███░░░ 20%");
 }

  if(player == 10)
 {
   printf("\n❤ ██░░░░ 10%");
 }

  if(player == 0)
 {
   printf("\n❤ ░░░░░░ 0%");
 }

}

/*
*    Barra de life do 2 usuario
  */


int Lifebarrae()
{
  
 if(enemy == 50)
 {
   printf("\n❤ ██████ 50%");
 }

  if(enemy == 40)
 {
   printf("\n❤ █████░ 40%");
 }

   if(enemy == 30)
 {
   printf("\n❤ ████░░ 30%");
 }

   if(enemy == 20)
 {
   printf("\n❤ ███░░░ 20%");
 }

  if(enemy == 10)
 {
   printf("\n❤ ██░░░░ 10%");
 }

  if(enemy == 0)
 {
    printf("\n❤ ░░░░░░ 0%");
 }

}

/*
*   junçoes das funções executada no main
  */


int pvp()
{
  
verefic();

  players();
  enemys();
 dadop();
  dadoe();
    
}


/*
*   Função principal
  */

int main ()
{
int gameover = 0;
 
   int key,i;
i = 0;

nome();
  
  printf("\ndigite 1 para começar a partida\n");
  scanf("\n\n%i", &key);

while( gameover == false){
  
  if(key == true)
  {
    system("clear");
    i++;
    printf("\n\n\t\t░░▒▓███ RODADA %i ███▓▒░░", i);
    pvp();
    sleep(ms+1);
  }
  if( player == 0)
  {
    system("clear");
    printf("\n---------------------------\n");
      printf("%s", string1);
    printf("_________/\n");
    printf("ganhou com %i de ♥️",enemy);
       printf("\n---------------------------\n");
    gameover = 1;
  } 
  if ( enemy == 0)
  {
     system("clear");
       printf("\n---------------------------\n");
    printf("%s", string2);
    printf("_________/\n");
    printf("ganhou com %i de ♥️",player);
       printf("\n---------------------------\n");
    gameover = 1;
  }
 
  }
 
  return 0;
}
