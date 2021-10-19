# -_-
Пользователь вводит строку и шаг сдвига. Шаг может быть как положительным, так и отрицательным для расшифровки.   В процессе написания, отладки и улучшения программы используйте git для фиксации изменений. Сопровождайте коммиты понятными комментариями о том, что было сделано.
#include<iostream>
#include<string.h>
using namespace std;
int main() {
   cout<<"Enter the message:\n";
   char msg[100];
   cin.getline(msg,100); 
   int i, j, length,choice,key;
   cout << "Enter key: ";
   cin >> key; 
   length = strlen(msg);
   cout<<"Enter your choice \n1. Encryption \n2. Decryption \n";
   cin>>choice;
   if (choice==1) 
      
      for(int i = 0; msg[i] != '\0'; ++i) {
         char ch;
		 ch = msg[i];
         if (ch >= 'a' && ch <= 'z') {
            ch = ch + key;
            if (ch > 'z') {
               ch = ch - 'z' + 'a' - 1;
            }  
            msg[i] = ch;
         }
         
         else if (ch >= 'A' && ch <= 'Z') {
            ch = ch + key;
            if (ch > 'Z') {
               ch = ch - 'Z' + 'A' - 1;
            }
            msg[i] = ch;
         }
		 printf("Encrypted message: %s", msg);
      }
      
   
     else if( choice==2) { 
      for(int i = 0; msg[i] != '\0'; ++i) {
         char ch;
		 ch = msg[i];
         if(ch >= 'a' && ch <= 'z') {
            ch = ch - key;
            if(ch < 'a'){
               ch = ch + 'z' - 'a' + 1;
            }
            msg[i] = ch;
         }
         else if(ch >= 'A' && ch <= 'Z') {
            ch = ch - key;
            if(ch < 'A') {
               ch = ch + 'Z' - 'A' + 1;
            }
            msg[i] = ch;
         }
      }
      cout << "Decrypted message: " << msg;
   }
}
