# sentence_generator.py

import nltk
import random

def load_words():
    nltk.download('words')
    from nltk.corpus import words
    return words.words()

def generate_example_sentences(word, num_sentences=5):
    english_words = load_words()
    word = word.lower()
    sentences = []

    for _ in range(num_sentences):
        sentence = []
        for _ in range(random.randint(5, 15)):
            new_word = random.choice(english_words)
            if new_word == word:
                continue
            sentence.append(new_word)

        sentence[random.randint(0, len(sentence) - 1)] = word
        sentence_str = " ".join(sentence) + "."
        sentences.append(sentence_str.capitalize())

    return sentences

if __name__ == "__main__":
    input_word = input("Enter a word: ")
    num_sentences = int(input("How many example sentences do you want? "))

    example_sentences = generate_example_sentences(input_word, num_sentences)
    print("\nExample sentences:")
    for sentence in example_sentences:
        print(sentence)

The program will prompt the user to enter a word and the number of example sentences the user wants. It will then generate random sentences containing the given word from the English dictionary. 
