# Function 1: Calculate the sum of numbers in a list
def calculate_sum(numbers):
    total = sum(numbers)
    return total


# Function 2: Calculate the average (mean) of numbers
def calculate_average(numbers):
    if len(numbers) == 0:
        return 0

    average = sum(numbers) / len(numbers)
    return average


# Function 3: Calculate the median and mode
def calculate_median_mode(numbers):
    if len(numbers) == 0:
        return None, None

    sorted_numbers = sorted(numbers)

    # Calculate Median
    n = len(sorted_numbers)
    middle = n // 2

    if n % 2 == 0:
        median = (sorted_numbers[middle - 1] +
                  sorted_numbers[middle]) / 2
    else:
        median = sorted_numbers[middle]

    # Calculate Mode
    frequency = {}
    for number in numbers:
        frequency[number] = frequency.get(number, 0) + 1

    highest_frequency = max(frequency.values())

    modes = [number for number, count in frequency.items()
             if count == highest_frequency]

    if highest_frequency == 1:
        mode = "No mode"
    else:
        mode = modes

    return median, mode


# Main Program
numbers = [10, 20, 30, 20, 40, 50]

print("Numbers:", numbers)
print("Sum:", calculate_sum(numbers))
print("Average:", calculate_average(numbers))

median, mode = calculate_median_mode(numbers)

print("Median:", median)
print("Mode:", mode)