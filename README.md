# Technical-Writing Assignment

// Introduction

   A lab I recently completed for my CS231 Computer Programming I class, a lab on user-implemented functions 
and how to execute them. The project posed the concept of coding a menu to display various options such as 
converting a hexadecimal number into a decimal number and vice versa. It also demanded that the programmer 
include a way to break out of the menu once the user is done using it, breaking out of the loop effectively.
The purpose of the lab was to teach programmers how to use user implemented functions, and how to use 
function signatures. 

// Methodology
    As mentioned in the introduction, the prompt called for us to complete the task by 1) creating a menu and 
2) Completing the various tasks each option called for. Firstly, I created the code for the header:

  int main(){

      // Implement Menu
      int option;
      do {
          cout << "\nPress 1) Convert Hexadecimal to Decimal." << endl;
          cout << "Press 2) Convert decimal to Hexaecimal." << endl;
          cout << "Press 0) To Exit." << endl;
          cin >> option;

This code created the option variable and is the first part of a "do-while" loop that runs the program menu. 
A Do-While loop creates an action to perform while the arguments being passed are true. The arguments being 
passed can be coded to have certain actions to be taken if the case is found to true. 
    The next part of the project consisted of making the functions for each of the options to be executed 
and calculated. The first option was to convert a decimal number into a Hexadecimal number. I began by 
prompting the user for some decimal input. I stored the user's input in a variable, and using that variable
I ran it through the function I had made to calculate the conversion. To correctly implement a function it 
must first be given a function signature, before the main function and implemented after the main function.
By implementing the function, it is essentially where the function's actions are constructed. 
    For the first function, Hexadecimal to Decimal conversion, I took the users input and saved the value 
in a variable. I also saved the value of the base 10 to a variable, as a decimal number is a base 10 
value. I then mused the .size() function from the <string> library to perform a function to iterate over 
the input and determine how many place values there are. Finally, (using the <cmath> library) I used a for 
loop to iterate over the place values and determine if there were any between the values of 'A' and 'F', 
telling the computer how to read those values and what numberic values they represented as well as how to 
convert them to a decimal number. The final product resulted in this code:

// Implementing Hex2Dec
int HextoDec(string hex){
    int decimal = 0;
    int base = 16;

    int len = hex.size(); // get the length of the string
    int p = 0;

    for(int i = len -1; i >= 0; i--){        // Hex = "1ABC" (first digit is 0, 2nd is 1, 3rd is 2. Counting left to right.)
        if(hex[i] >= '0' && hex[i] <= '9'){
            decimal = decimal + (hex[i] - '0') * pow(base, p); // or len - 1 - 1
            p++;
        } else if (hex[i] >= 'A' && hex[i] <= 'F') {
            decimal = decimal + (hex[i] - 'A' + 10) * pow(base, p);
            p++;
        } else if (hex[i] >= 'a' && hex[i] <= 'f') {
            decimal = decimal + (hex[i] - 'a' + 10) * pow(base, p);
            p++;
        }

    }        
    return decimal;
    }

  
  The seond option for the menu is to convert a decimal number to a hexadecimal number. This was done in 
essentially the same way the first function was implemented. Using a while loop, and while the arguement 
of the users inputted hexadecimal number is true. The function takes that value and gets the remainder of
the value divided by base 16. Storing that remainder's value, an if-else loop was created. If the remainder
was less than 0 that value is just used, otherwise it is added the the Hex value 'A' and 10 is subtracted.
The decimal value is then divided again by 16 until the loop is found to be false and broken. Then that value
is returned to the user. This is shown in the following code: 

    // Implement DectoHex
    string DectoHex(int decimal){
        string hex = "";
        while (decimal > 0) {
            int remainder = decimal % 10;
            if (remainder < 10){
                hex = to_string(remainder) + hex;
            } else {
                hex = (char)('A' + remainder - 10) + hex;
        }
        decimal = decimal / 16; 
    }
    return hex;

// Results

  The results of the program and the assignment were a success. The program ran and compiled without error and
ended up being completely functional. The user was able to navigate the menu as many times as they wished and 
was able to connvert any value to the other. The menu was also able to be broken out of when the correct option
was selected. The program compiling as planned was significant because it indicated all required fields of the 
prompt and assignment had been met, completed, and executed. 

// Conclusion

  In conclusion, the prompt was to create a menu that had multiple selections to convert decimal numbers to 
hexadecimal and hexadecimal numbers to decimal. The program taught me how to implement functions as well as
how to create function signatures. These skilled enlightened my knowledge of programming and how to create
more efficient code using user-defined functions. It also increased my knowledge of the various different 
libraries at the disposal of C++ programmers, to use those libraries to implement pre-made functions 
inside those libraries. 

