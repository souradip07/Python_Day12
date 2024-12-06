# Python_Day12

#Example Code for Advanced Calculations:
import math

# Calculate square root
number = 16
sqrt_result = math.sqrt(number)
print(f"The square root of {number} is {sqrt_result}")

# Calculate sine of 45 degrees (converted to radians)
angle_degrees = 45
angle_radians = math.radians(angle_degrees)
sine_result = math.sin(angle_radians)
print(f"The sine of {angle_degrees} degrees is {sine_result}")

# Calculate natural logarithm of a numbe
number = 10
log_result = math.log(number)
print(f"The natural logarithm of {number} is {log_result}")


#Example Code for Extended Signal Calculator:
import math
import random

def calculate_statistics(signal_readings):
    """
    Calculate statistical metrics for signal readings.
    
    Parameters:
    signal_readings (list): A list of signal readings.
    
    Returns:
    dict: A dictionary containing the mean, standard deviation, and variance.
    """
    if not signal_readings:
        return {"mean": None, "std_dev": None, "variance": None}
    
    mean = sum(signal_readings) / len(signal_readings)
    variance = sum((x - mean) ** 2 for x in signal_readings) / len(signal_readings)
    std_dev = math.sqrt(variance)
    
    return {"mean": mean, "std_dev": std_dev, "variance": variance}

def generate_random_signals(count, lower_bound, upper_bound):
    """
    Generate a list of random signal readings.
    
    Parameters:
    count (int): Number of random signal readings to generate.
    lower_bound (float): Lower bound of the signal value range.
    upper_bound (float): Upper bound of the signal value range.
    
    Returns:
    list: A list of random signal readings.
    """
    return [random.uniform(lower_bound, upper_bound) for _ in range(count)]

# Example usage:
random_signals = generate_random_signals(10, 0, 100)
print(f"Random signal readings: {random_signals}")

stats = calculate_statistics(random_signals)
print(f"Mean: {stats['mean']:.2f}, Std Dev: {stats['std_dev']:.2f}, Variance: {stats['variance']:.2f}")
