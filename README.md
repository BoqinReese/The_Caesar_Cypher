# The_Caesar_Cypher
# A program to encrypt or decrypt a message.
"""
How it works
    To encrypt, it gets the position of the character in the alphabet, then adds the encryption key to that value.
It then finds the letter represented by the result in the alphabet. If the result is more than the max value in the
alphabet, It subtracts the length of the alphabet from that value and gets the letter represented by the new value.
    To decrypt, it simply subtracts the encryption key from the value got by adding the key to the value of the letter.
If the subtracted value is less than zero, then it adds the value of the length of the alphabet. That will get the
original letter's index.
"""

import string

alphabet = string.ascii_uppercase
secret = input('Enter ur secret message: ')
secret = secret.upper()
key = int(input('Enter ur encryption key: '))
action = input('Enter "ENCRYPT" to encrypt and "DECRYPT" to decrypt: ')
action = action.upper()
result = ''
for letter in secret:
    if letter in alphabet:
        num = alphabet.find(letter)  # This gets and stores the position(index) of the letter in the alphabet variable
        if action == 'ENCRYPT':
            num += key
            if num < len(alphabet) and num > 0:
                result += alphabet[num]
            elif num >= len(alphabet):
                num -= len(alphabet)
                result += alphabet[num]
            elif num < 0:
                num += len(alphabet)
                result += alphabet[num]
        elif action == 'DECRYPT':
            num = num - key
            if num < len(alphabet) and num > 0:
                result += alphabet[num]
            if num >= len(alphabet):
                num -= len(alphabet)
                result += alphabet[num]
            elif num < 0:
                num += len(alphabet)
                result += alphabet[num]
            elif num == 0:
                result += alphabet[num]
    else:
        result += letter
print(result)

# Coded by @BoqinReese
