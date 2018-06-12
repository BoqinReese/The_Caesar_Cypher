# The_Caesar_Cypher
# A program to encrypt or decrypt a message.

How it works
    To encrypt, it gets the position of the character in the alphabet, then adds the encryption key to that value.
It then finds the letter represented by the result in the alphabet. If the result is more than the max value in the
alphabet, It subtracts the length of the alphabet from that value and gets the letter represented by the new value.
    To decrypt, it simply subtracts the encryption key from the value got by adding the key to the value of the letter.
If the subtracted value is less than zero, then it adds the value of the length of the alphabet. That will get the
original letter's index.
