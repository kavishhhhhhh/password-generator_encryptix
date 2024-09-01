# password-generator_encryptix
import random
import string

def generate_password(length):
    characters = string.ascii_letters + string.digits + string.punctuation
    
    password = ''.join(random.choice(characters) for i in range(length))
    
    return password

def password_generator():
    while True:
        try:
            length = int(input("Enter the desired password length: "))
            if length < 1:
                print("Password length must be greater than 0. Please try again.")
                continue

            password = generate_password(length)
            print(f"Generated Password: {password}")

            another = input("Do you want to generate another password? (yes or no): ").lower()
            if another != 'yes':
                break
        except ValueError:
            print("Please enter a valid number.")

    print("Thanks for using the Password Generator!")

password_generator()
