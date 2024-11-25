# Hangman !

Welcome to this page.

Todays coding session contains 3 exercises. Don't worry about how far you get it. All that matters is the effort you put into it.

## Exercise 1 - Run code on google collab
- Go to https://colab.research.google.com and create a notebook
- Copy the code below into the notebook
  - copy it **exactly** as it stands 
  - When you are done, press run (▶)
- You will likely get an error, and that is completely okay
- Try to find the typo that caused the error and fix it

## Exercise 2 - Run code locally
- install python on your computer
  - go to [this link](https://docs.anaconda.com/anaconda/install/#basic-install-instructions) and follow the instructions.
- open TextEdit (MacOS) or Notepad (Windows)
  - copy paste the code below into a new file called main.py
  - open your terminal and navigate to the location of that the file
  - run `python main.py`

## Exercise 3 - Modify the code
- In the code below the secret word is fixed. This is a bit borring and can improved. Try changing the code so that `secret_word` changes every time you run the program.
- hint: [look at this code](https://www.w3schools.com/python/ref_random_choice.asp) for inspiration

```python
# My first Python program
name = input('What is your name? ')
print('Hello, ' + name + '. Time to play hangman!')
print('Start guessing...')

secret_word = 'secret'
guesses = ''
turns = 10

while turns > 0:
    failed = 0

    for char in secret_word:
        if char in guesses:
            print(char, end='')
        else:
            print('_', end='')
            failed += 1

    if failed == 0:
        print('\nYou won!')
        break

    print()
    guess = input('guess a character: ')

    if len(guess) > 1:
        print('Only one character at the time, please!')
        continue

    guesses += guess

    if guess not in secret_word:
        turns -= 1
        print('Wrong\n')
        print('You have', turns, 'more guesses')
        if turns == 0:
            print('You lose!')
```