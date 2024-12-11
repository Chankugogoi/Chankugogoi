import random

# Function to choose a multiplier value between 1.2 and 30
def choose_multiplier():
    # Create values between 1.2 and 30, with steps of 0.1 to cover a reasonable range of numbers.
    multipliers = [i * 0.1 for i in range(12, 301)]  # Values from 1.2 to 30
    # Create weights, giving higher probability to values <= 5 and lower to values > 5
    weights = [1.5 if m <= 5 else 0.5 for m in multipliers]
    
    # Use random.choices() to pick a weighted multiplier
    return random.choices(multipliers, weights)[0]

# Function to choose a number between 1 and 30
def choose_number():
    # List values from 1 to 30
    numbers = list(range(1, 31))
    # Create weights: higher probability for values <= 15, lower for values > 15
    weights = [1.5 if n <= 15 else 0.5 for n in numbers]
    
    # Use random.choices() to pick a weighted number 2

    return random.choices(numbers, weights)[0]

# Example usage
multiplier = choose_multiplier()
number = choose_number()

print(f"Chosen multiplier: {multiplier}")
print(f"Chosen number: {number}")
