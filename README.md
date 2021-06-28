# Notecards

I'm writing this program to help me study Spanish.

## Input Spanish accents into the terminal on a Mac

1. Press `option + e`
2. Press the vowel to accent (shift for capital)
3. Example output: `áéíóúÁÉÍÓÚ`

## High Level Design

- I can create a spreadsheet with Spanish and English vocabulary
- I can export the spreadsheet into a csv
- I can import the csv into my program
- My program will seed a database with the csv file
- When the database is seeded, I can run my program from the command line
- The program has a menu interface to Quit
- The program has a menu interface to select Spanish to English or English to Spanish
- The program has a menu interface to select a unique chapter/unit of vocabulary
- When I select a chapter/unit, 10 notecards are chosen from the deck belonging to that unit
- I am shown vocabulary in one language and prompted to input the translation in the other language
- When I press return, I am prompted with the next notecard
- When all 10 notecards are completed, I am taken to a results interface that shows me my score out of 10
- The results interface shows in three columns: the vocabulary in question, the correct translation, and a result of X or O for wrong or right, respectively
- After my results are shown, I am prompted to return to the main menu or quit

## Mid Level Design (In progress)

### Classes

#### Notecard

##### Properties

- .vocabulary, string
  - it is the vocabulary in question
- .translation, string
  - it is the translation to the vocabulary

##### Behaviors  



#### Deck

##### Properties

- .notecards, list
  - holds 10 notecards
- .is_empty, boolean
  - TRUE when .notecards is empty
  - FALSE otherwise
- .top_deck, obj
  - it is .notecards[0]

##### Behaviors

- show_top_deck()
  - displays the vocabulary of .top_deck
- pop()
  - removes and returns .top_deck
    - this goes to Board.notecards

#### Board

##### Properties

- .notecards, list
  - it takes Notecard objs from the Deck (?)
- .attempt, string
  - it is a user input
- .is_correct, boolean
  - O / TRUE when attempt == translation
  - X / FALSE otherwise
- .results, list
  - it is a list of tuples
    - ('el perro', 'dog', O)
    - ('el gato', 'dog', X)
    - (vocabulary, attempt, is_correct)

##### Behaviors

- get_attempt()
  - prompts user for input
- check_attempt()
  - the attempt is compared to the translation
- set_result()
  - appends a tuple to .results
- show_results()
  - shows all results