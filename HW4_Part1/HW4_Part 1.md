```python
## Day 1: Sonar Sweep (Part 1)
```

    The number of times the depth increases is: 1559
    


```python
# Directly specifying the absolute path to the file
file_path = 'C:\\Users\\student\\Desktop\\HW4_PART1\\input.txt'

# Function to read depths from the file
def read_depths(file_path):
    with open(file_path, 'r') as file:
        # Read all lines in the file and convert them to integers
        depths = [int(line.strip()) for line in file.readlines()]
    return depths

# Function to count the number of times the depth increases
def count_increases(depths):
    increases = 0
    # Compare each value with the value before it
    for i in range(1, len(depths)):
        if depths[i] > depths[i - 1]:
            increases += 1
    return increases

# Using the function to read data
depths = read_depths(file_path)

# Calculating the increases and printing the result
increase_count = count_increases(depths)
print(f"The number of times the depth increases is: {increase_count}")

```

    The number of times the depth increases is: 1559
    

##  Part Two


```python
def read_and_calculate_sums(file_path):
    # Read the file and calculate the sums of three consecutive measurements
    with open(file_path, 'r') as file:
        depths = [int(line.strip()) for line in file.readlines()]
    window_sums = []
    for i in range(len(depths) - 2):
        # Sum the current and the next two measurements
        window_sum = depths[i] + depths[i+1] + depths[i+2]
        window_sums.append(window_sum)
    return window_sums

def count_increases(window_sums):
    # Count how many times the sum increases compared to the previous sum
    increases = 0
    for i in range(1, len(window_sums)):
        if window_sums[i] > window_sums[i-1]:
            increases += 1
    return increases

# Simplified file path variable for clarity
file_path = 'C:\\Users\\student\\Desktop\\HW4_PART1\\input.txt (2).txt'

# Read the file and calculate the window sums in one step
window_sums = read_and_calculate_sums(file_path)

# Count the number of increases in window sums
increase_count = count_increases(window_sums)

# Output the result to the user
print(f"The number of sums that are larger than the previous sum is: {increase_count}")

```

    The number of sums that are larger than the previous sum is: 1600
    


```python

```
