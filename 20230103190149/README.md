## Python Error handling 

* Asked ChatGTP for a try block and it gave me a nice code block 

```
while True:
    try:
        user_input = int(input("Enter a number between 1 and 3: "))
        if 1 <= user_input <= 3:
            # Input is valid, we can exit the loop
            break
        else:
            print("Invalid input. Please try again.")
    except ValueError:
        print("Invalid input. Please enter a valid number.")

print("Thank you for entering a valid number.")
```
* This will keep asking the user for input until they provide a valid number between 1 and 3. If the user enters a valid number, the loop will break and the program will continue execution. If the user enters an invalid input (e.g. a non-numeric string or a number outside the range 1 to 3), the except block will handle the ValueError exception and ask the user to try again.


