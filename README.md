import re
import math

def solve_math_expression(expression):
    try:
        result = eval(expression)
        return result
    except:
        return "Invalid expression or operation."

def main():
    print("Trigonometric Questions Solver Bot")
    print("Type 'exit' to quit.")

    trig_identities = [
        # Pythagorean Identities
        {"question": "sin^2(θ) + cos^2(θ)", "expression": "1", "variables": {"θ": 0}},
        {"question": "tan^2(θ) + 1", "expression": "sec^2(θ)", "variables": {"θ": 0}},
        {"question": "cot^2(θ) + 1", "expression": "csc^2(θ)", "variables": {"θ": 0}},

        # Reciprocal Identities
        {"question": "csc(θ)", "expression": "1 / sin(θ)", "variables": {"θ": 0}},
        {"question": "sec(θ)", "expression": "1 / cos(θ)", "variables": {"θ": 0}},
        {"question": "cot(θ)", "expression": "1 / tan(θ)", "variables": {"θ": 0}},

        # Quotient Identities
        {"question": "tan(θ)", "expression": "sin(θ) / cos(θ)", "variables": {"θ": 0}},
        {"question": "cot(θ)", "expression": "cos(θ) / sin(θ)", "variables": {"θ": 0}},

        # Co-Function Identities
        {"question": "sin(π/2 - θ)", "expression": "cos(θ)", "variables": {"θ": 0}},
        {"question": "cos(π/2 - θ)", "expression": "sin(θ)", "variables": {"θ": 0}},
        {"question": "tan(π/2 - θ)", "expression": "1 / tan(θ)", "variables": {"θ": 0}},
        {"question": "cot(π/2 - θ)", "expression": "1 / cot(θ)", "variables": {"θ": 0}},

        # Double Angle Identities
        {"question": "sin(2θ)", "expression": "2 * sin(θ) * cos(θ)", "variables": {"θ": 0}},
        {"question": "cos(2θ)", "expression": "cos(θ)**2 - sin(θ)**2", "variables": {"θ": 0}},
        {"question": "tan(2θ)", "expression": "2 * tan(θ) / (1 - tan(θ)**2)", "variables": {"θ": 0}},

        # Half Angle Identities
        {"question": "sin(θ/2)", "expression": "sqrt((1 - cos(θ)) / 2)", "variables": {"θ": 0}},
        {"question": "cos(θ/2)", "expression": "sqrt((1 + cos(θ)) / 2)", "variables": {"θ": 0}},
        {"question": "tan(θ/2)", "expression": "sqrt((1 - cos(θ)) / (1 + cos(θ)))", "variables": {"θ": 0}},

        # Sum and Difference Identities
        # ... Add more identities here ...

        # Product-to-Sum Identities
        # ... Add more identities here ...
    ]

    while True:
        user_input = input("Enter a math question: ")

        if user_input.lower() == "exit":
            print("Exiting the bot.")
            break

        for identity in trig_identities:
            if identity["question"] in user_input:
                expression = identity["expression"]
                for variable, value in identity["variables"].items():
                    expression = expression.replace(variable, str(value))
                result = solve_math_expression(expression)
                print("Answer:", result)
                break
        else:
            print("Identity not recognized. Please enter a valid trigonometric identity.")

if __name__ == "__main__":
    main()
    
