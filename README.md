# periodic_table_encryption_code

# A DESCRIPTION OF THE PROJECT: this is a pretty basic code that encrypts a password based off of your first name, gender and current age. I used an edited periodic table as the key to encrypt this. Not going to give away too much but I took 26 elements from the periodic tables along with their corresponding numbers. I chose the 26 elements based on what letter they started with, hence there being 26 of them. I then take their name, age, and gender and use that to make the unique ID. I use the two letters of your name, use the corresponding number in the edited periodic table I made. I then add your current age to the ID. Finally, based on your gender(He for male which is the symbol for Helium, Helium's periodic table number is 2) and(La for female, this is the symbol for Lanthanum, Lanthanum's periodic table number is 57. I chose La due to it being the beginning of Lady). Alright let's move onto the code. 

#all inputs from the user, they will be stored in user_info list

user_name = str(input("Enter your name to encrypt it(all lowercase): "))
age = int(input("Enter your age as a number: "))
gender = str(input("Are you male or female?: "))

#list that holds all info that the user entered

user_info = list([user_name, age, gender])

#dictonary that holds periodic table symbols and numbers

periodic_table = {
    "a" : 89,
    "b": 5,
    "c": 6,
    "d": 105,
    "e": 68,
    "f": 9,
    "g": 31,
    "h": 1,
    "i": 53,
    "j": 119,
    "k": 19,
    "l": 57,
    "m": 115,
    "n": 7,
    "o": 8,
    "p": 15,
    "q": 120,
    "r": 88,
    "s": 16,
    "t": 73,
    "u": 92,
    "v": 23,
    "w": 74,
    "x": 54,
    "y": 39,
    "z": 30,
}


#list to hold individual letters of inputed name

indiv_letters = []

#simple function off google that splits your string into individual letters. I edited it to fit my needs

def split(word):
    return [char for char in word]

word = user_name
indiv_letters = split(word)

#finds first and last letters of inputed string/name

length = len(indiv_letters)
first_letter = (indiv_letters[0])
last_letter = (indiv_letters[length-1])

#seperates respective values in the periodic table dictionary

first_letter_value = periodic_table[first_letter]
last_letter_value = periodic_table[last_letter]

#takes both letter values and adds them together as strings

first_letter_str = str(first_letter_value)
last_letter_str = str(last_letter_value)

#a variable to hold whatever number your gender corresponds with

gender_number = 0

#depending on what you entered, assigns a periodic table value to your gender
if gender == "male" or "Male":
    #use He(Helium) for a "boy" AKA male which corresponds to 2
    #use La(Lanthanum) for a "lady" AKA female which corresponds to 57
    gender_number = 2
else:
    gender_number = 57

#prints values as a combined string

print("")
code_based_off_name = print("Your encrypted code is: " + first_letter_str+last_letter_str+str(age)+str(gender_number))





#I plan on continuing this project by making a login system using Tkinter module in python. You will enter your username and this info and it will give you a password, the user ID. This way it's impossible to forget your password as you can just figure it out using your name, gender and age. If I ever decide to use this as a viable password creation method I will refactor the formula and use different elements as the key is being made public by me right now haha.

