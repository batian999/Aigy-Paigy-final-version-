# Aigy-Paigy-final-version-

# Fuchun Yang 
# 10/29/2018

# function 
# This is a function that tests if the character in the phrase is a vowel or not. 
# If the character is a vowel, this function will return true. If the character is not a vowel, it will return false. 
def Aigy_Paigy(character):
    for i in range (len(vowel)):
        if character == vowel[i]:
            return True 
    return False



# main 
# This is to tell the user to input a phrase.     
phrase = input("Enter a phrase to turn into Aigy-Paigy or -1 to stop: ")
vowel = ['a','e','i','o','u']
# This new phrase is to record the phrase in aigy paigy form.
# So I will make it a blank. 
new_phrase = " "
# This while loop is to ask the user to infinitely input a phrase until the user input -1 to stop. 
while phrase != '-1':
# This is to reset the new phrase every time so that the last aigy-paigy word won't be combined with the next one. 
    new_phrase = " "
# This for loop is to put the characters in the phrase into the function.
    for i in range(len(phrase)):
# This is to examine whether the character examined is a vowel. If it is, it will return true.
# so I will further examine whether the successive character is a vowel. If the second character is also a vowel,
# I will add aig+current character+next character to the new phrase. If only the current one is vowel, I will only add
# aig+current character to the new phrase
# If the character is not a vowel, I will just add the character into the phrase. 
        if Aigy_Paigy(phrase[i]):
# This is a prerequisite that the ith character is not the last character in the phrase in case of that 
# the last character is a vowel and could not further examine if the next character is a vowel or not. 
            if i != len(phrase)-1:
                if Aigy_Paigy(phrase[i+1]):
                    new_phrase = new_phrase + 'aig' + phrase[i] + phrase[i+1]
# if the ith character is the last word in the phrase, I will check if i-1 term character is a vowel or not. 
# if the i-1 term is a vowel, do nothing because we've already added aig in front of the first vowel of two successive vowels. 
# if the i-1 term is not a vowel, then add aig before the character. 
            else: 
                if Aigy_Paigy(phrase[i-1]):
                    new_phrase = new_phrase + ""
                else:
                    new_phrase = new_phrase +'aig' + phrase[i] 
        else:
            new_phrase = new_phrase + phrase[i]
                        
    print(new_phrase)
# this input phrase is put here is because we want to ask the user to input something after the printing of the last aigy-paigy. 
    phrase = input("Enter a phrase to turn into Aigy-Paigy or -1 to stop: ")

    


