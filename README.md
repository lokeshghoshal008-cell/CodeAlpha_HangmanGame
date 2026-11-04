
import random

words = ["apple", "python", "cricket", "computer", "school"]

secret_word = random.choice(words)
guessed_letters = []
wrong_guesses = 0
max_attempts = 6

print("=== HANGMAN GAME ===")

while wrong_guesses < max_attempts:
    display = " ".join(
        letter if letter in guessed_letters else "_"
        for letter in secret_word
    )

    print("\nWord:", display)
    print("Wrong guesses:", wrong_guesses)

    if all(letter in guessed_letters for letter in secret_word):
        print("Congratulations! You won!")
        break

    guess = input("Guess one letter: ").lower().strip()

    if len(guess) != 1 or not guess.isalpha():
        print("Enter only one letter.")
        continue

    if guess in guessed_letters:
        print("You already guessed that letter.")
        continue

    guessed_letters.append(guess)

    if guess in secret_word:
        print("Correct guess!")
    else:
        wrong_guesses += 1
        print("Wrong guess!")
else:
    print("Game Over!")
    print("The word was:", secret_word)
# CodeAlpha_HangmanGame
e text-based Hangman game built using
