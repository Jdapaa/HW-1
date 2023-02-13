# HW-1
Assignment 1 with python code

    import string
    import random

    def picksome(n, s):
     # randomly selects n characters from the string s
     # returns them in another string
     res = ''.join(random.choices(s, k=n))
     return res

    def puttogether(forpswrd):
        # given string pswrd, randomly reorders the characters returns the new string
        shuffled_pswrd = list(forpswrd)
        random.shuffle(shuffled_pswrd)
        return''.join(shuffled_pswrd)

    def main():
        pswrdLen = int(input('What is the length of the password?: '))
        upcLen = int(input('How many uppercase letters?: '))
        locLen = int(input('How many lowercase letters?: '))
        digLen = int(input('How many digits?: '))

        print('Your password will have {} uppercase letters,'
              ' {} lower case letters,'
              '{} digits, ane one special character,'
              .format(upcLen, locLen, digLen))

        print('Is this correct? ')
        confirm = input('Yes or no: ')

        for i in range(4):
            uppercaseLetters = picksome(upcLen, string.ascii_uppercase)
            lowercaseLetters = picksome(locLen, string.ascii_lowercase)
            digits = picksome(digLen, string.digits)
            special = picksome(1, string.punctuation)

            forpswrd = puttogether(uppercaseLetters+lowercaseLetters+digits+special)
            final_password = (forpswrd)

            print(final_password)

    main()
