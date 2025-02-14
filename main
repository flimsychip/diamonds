#include <iostream> 
using namespace std;

const unsigned int max_width = 120;
const char  background_char = '.';
const char  main_char = '*';
const char  main_char_left = '/';
const char  main_char_right = '\\';

/* function prototype declarations (defined below in same file) */
void printArray (const char chArray[], const unsigned int width);

void fillArray (char fill, char chArray[], unsigned int width);

void fillArray (char fill, char chArray[], unsigned int start, unsigned int end);

int main() 
{ 
	unsigned int width = 0;
	
	// validate
	cout << "Enter width of diamond: ";
	cin >> width;
   if(width > max_width) {
      cout << "Error! Max width is " << max_width << ". Exiting." << endl;
      return 1;
   }
   
   char diamond[width][width];
   int startingSpace = width / 2;

   // start by filling background
   for(int i = 0; i < width; i++) {
      fillArray(background_char, diamond[i], width);
   }
   
   // change certain chars to main char
   if(width % 2 != 0) { // case: odd
      for(int i = 0; i < width/2+1; i++) {
         fillArray(main_char, diamond[i], startingSpace, width - startingSpace);
         startingSpace--;
      }
      for(int i = width/2-1; i < width; i++) {
         fillArray(main_char, diamond[i], startingSpace, width - startingSpace);
         startingSpace++;
      }
   } else { // case: even
      startingSpace--;
      for(int i = 0; i < width / 2; i++) {
         fillArray(main_char_left, diamond[i], startingSpace, width / 2);
         fillArray(main_char_right, diamond[i], width / 2, width - startingSpace);
         startingSpace--;
      }
      startingSpace = 0;
      for(int i = width / 2; i < width; i++) {
         fillArray(main_char_right, diamond[i], startingSpace, width / 2);
         fillArray(main_char_left, diamond[i], width / 2, width - startingSpace);
         startingSpace++;
      }
   }

	for(int i = 0; i < width; i++) {
	   printArray(diamond[i], width);
	   cout << endl;
	}
	return 0; 
}
 
void printArray (const char chArray[], const unsigned int width) {
   for(int i = 0; i < width; i++) {
         cout << chArray[i];
   }
}

void fillArray (char fill, char chArray[], unsigned int width) {
   for(int i = 0; i < width; i++) {
      chArray[i] = fill;   
   }
}

void fillArray (char fill, char chArray[], unsigned int start, unsigned int end) {
   for(int i = start; i < end; i++) {
      chArray[i] = fill;   
   }
}
