// Program-that-Validates-a-Student-ID
// This C++ program allows people to validate an ID Number by using a string, boolean, characters, integers and a while, if, for and switch loop
#include <iostream>
using namespace std;
   
  int main()
  {
     string sID; //string is used so user can enter as many characters as possible
     int i, len;
     char letter, choice;
     bool validID; // program continues until user input is incorrect, then validID is false
  
     choice = 'Y';
  
  while(choice == 'Y' || choice == 'y')
  {
     cout << "Enter a University ID String ie.[L-NNNNNNNNN (11 characters)] : ";
     cin >> sID;  // multiple characters, duh
  
     validID = true;
     len = sID.length(); //length is already a function, len is equal to the amount of characters the user has inputed
  
     if (len == 11 && (choice == 'Y' || 'y')) // length MUST be 11 characters 
     {
        for (i=0;i < len;i++) // i is that random integer for the for loop
        {
           letter = sID.at(i); // the i is called in the sID.at 
  
           switch (i)  // ok folks. This i right here... allows one to use case statements but each switch statement corr    esponds to each character that the user has inputed 
           {
              case 0:
                  if (!(letter >= 'A' and letter <= 'Z'))
                  {
                          validID = false;
                  }
                  break;
              case 1:
                  if (letter != '-')
                  {
                          validID = false;
                  }
                  break;
              case 2:
                 if (!(letter >= '0' and letter <= '9'))
                 {
                    validID = false;
                 }
  
              break;
  
              case 3:
              case 4:
              case 5:
              case 6:
              case 7:
              case 8:
              case 9:
              case 10:
  
              break; // ends program, super useful for a while and switch loop
           }
        }
  
        if (validID == true)
           cout << "OK. It is a valid University ID Number" << endl; // User followed the example. Gold Star!
        else
           cout << "It is NOT a valid University ID Number!" << endl; // If user enters in 11 characters but screws up
     }
     else
     {
        cout << "It is NOT a valid University ID Number!" << endl; // If user  does not enter in 11 characters
     }
  
        cout << "Check another University ID number? (Y = yes N = no) : ";
        cin  >> choice;
  }
  
  if(choice == 'N' || 'n')
  {
          cout << " Have a nice day! " << endl;
  }
     return 0;
  }
