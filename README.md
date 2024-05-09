# password-generator
import random
import string
import pyperclip

def generate_password(length, uppercase, lowercase, numbers,special):
    characters = ''
    if uppercase:
        characters += string.ascii_uppercase
    if lowercase:
        characters += string.ascii_lowercase
    if numbers:
        characters += string.digits
    if special:
        characters += string.punctuation

    if not characters:
        print("Error: To select at least one character in type.")
        return None

    password = ''.join(random.choice(characters) for _ in range(length))
    return password

def main():
    print("welcome to randomised Password Generator!")
    length = int(input("Enter the length of the password: "))
    uppercase = input("Include uppercase letters? (yes/no): ").lower() == 'yes'
    lowercase = input("Include lowercase letters? (yes/no): ").lower() == 'yes'
    numbers = input("Include numbers? (yes/no): ").lower() == 'yes'
    special = input("Include special characters? (yes/no): ").lower() == 'yes'

    password = generate_password(length, uppercase, lowercase, numbers, special)
    if password:
        print("Generated Password:", password)
        pyperclip.copy(password)
        print("Password copied to clipboard! ready yor password")

if __name__ == "__main__":
    main()
