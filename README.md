# Internship_projects
import random
import string

def generate_password(length, use_uppercase=True, use_lowercase=True, use_numbers=True, use_symbols=True):
    """Generate a random password based on specified criteria."""
    # Define character sets
    characters = []
    if use_uppercase:
        characters.extend(string.ascii_uppercase)
    if use_lowercase:
        characters.extend(string.ascii_lowercase)
    if use_numbers:
        characters.extend(string.digits)
    if use_symbols:
        characters.extend(string.punctuation)

    # Check if at least one character set is selected
    if not characters:
        print("Error: At least one character type must be selected.")
        return None

    # Generate password
    password = ''.join(random.choice(characters) for _ in range(length))
    return password

def main():
    print("Welcome to the Random Password Generator!")

    # User inputs
    length = int(input("Enter the desired length of the password: "))
    use_uppercase = input("Include uppercase letters? (yes/no): ").lower() == 'yes'
    use_lowercase = input("Include lowercase letters? (yes/no): ").lower() == 'yes'
    use_numbers = input("Include numbers? (yes/no): ").lower() == 'yes'
    use_symbols = input("Include special characters? (yes/no): ").lower() == 'yes'

    # Generate password
    password = generate_password(length, use_uppercase, use_lowercase, use_numbers, use_symbols)
    if password:
        print(f"Generated Password: {password}")

if __name__ == "__main__":
    main()
