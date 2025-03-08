import itertools
import string

def brute_force(password, max_length=8):
    chars = string.ascii_letters + string.digits + string.punctuation
    attempts = 0
    for length in range(1, max_length + 1):
        for guess in itertools.product(chars, repeat=length):
            attempts += 1
            guess = ''.join(guess)
            if guess == password:
                return f"Password found: {guess} (Attempts: {attempts})"
            print(f"Attempt {attempts}: {guess}")
    return "Password not found."

if __name__ == "__main__":
    target_password = "pass123"
    result = brute_force(target_password)
    print(result)
