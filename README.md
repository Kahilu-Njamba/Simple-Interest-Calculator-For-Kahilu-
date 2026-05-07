# Simple-Interest-Calculator-For-Kahilu-
simple Interest Calculator created for a student named Kahilu Joseph Njamba, which generate simple interest given the principal amount, Annual interest amount and Time in years.

import time

first_name = 'Kahilu'
middle_name = 'Joseph'
last_name = 'Njamba'
my_name = f"{first_name} {middle_name} {last_name}"
student_name = my_name
other_student_details = {
    "School name": "KNU",
    "Student number": "20253623",
    "Gender": "male",
    "Status": "single"
}

def slow_print(text, delay=0.03):
    for char in text:
        print(char, end='', flush=True)
        time.sleep(delay)
    print()

def show_menu():
    slow_print("\n=== Simple Interest Calculator ===")
    slow_print(f"  Welcome, {student_name}!")
    slow_print("==================================")
    slow_print("1. Enter Principal Amount (P)")
    slow_print("2. Enter Annual Interest Rate (R)")
    slow_print("3. Enter Time in Years (T)")
    slow_print("0. Exit")
    slow_print("==================================\n")

def get_float_input(prompt):
    while True:
        try:
            value = float(input(prompt))
            if value <= 0:
                print(f"Please enter a positive number, {first_name}.")
            else:
                return value
        except ValueError:
            print(f"Invalid input. Please enter a numerical value, {first_name}.")

while True:
    show_menu()

    choice = input("Choose an option (or press Enter to calculate): ").strip()

    if choice == '0':
        slow_print(f"\nGoodbye, {first_name}! See you next time.")
        break

    P = get_float_input("Enter principal amount (P): ")
    R = get_float_input("Enter annual interest rate (R): ")
    T = get_float_input("Enter time in years (T): ")

    SI = (P * R * T) / 100
    slow_print(f"\n--- Result for {student_name} ---")
    slow_print(f"Simple Interest: {SI:.2f}")
    slow_print("--------------------------------\n")

    again = input("Calculate again? (yes/no): ").strip().lower()
    if again != 'yes':
        slow_print(f"\nGoodbye, {first_name}! See you next time.")
        break
