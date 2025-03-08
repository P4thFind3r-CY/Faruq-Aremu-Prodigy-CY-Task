import re

def check_password_strength(password):
    # Define password strength criteria
    length_criteria = len(password) >= 8
    uppercase_criteria = bool(re.search(r'[A-Z]', password))
    lowercase_criteria = bool(re.search(r'[a-z]', password))
    number_criteria = bool(re.search(r'\d', password))
    special_character_criteria = bool(re.search(r'[!@#$%^&*(),.?":{}|<>]', password))

    # Assess password strength
    strength_score = sum([
        length_criteria,
        uppercase_criteria,
        lowercase_criteria,
        number_criteria,
        special_character_criteria
    ])

    # Provide feedback based on score
    if strength_score == 5:
        strength_message = "Very Strong"
    elif strength_score == 4:
        strength_message = "Strong"
    elif strength_score == 3:
        strength_message = "Moderate"
    elif strength_score == 2:
        strength_message = "Weak"
    else:
        strength_message = "Very Weak"

    # Detailed feedback for users
    feedback = []
    if not length_criteria:
        feedback.append("Increase the password length to at least 8 characters.")
    if not uppercase_criteria:
        feedback.append("Add at least one uppercase letter.")
    if not lowercase_criteria:
        feedback.append("Add at least one lowercase letter.")
    if not number_criteria:
        feedback.append("Include at least one number.")
    if not special_character_criteria:
        feedback.append("Use at least one special character (!@#$%^&*(),.?\":{}|<>) for better security.")

    # Return the result
    return {
        "strength": strength_message,
        "feedback": feedback
    }

if __name__ == "__main__":
    # Get user input
    password = input("Enter a password to check its strength: ")
    result = check_password_strength(password)

    # Display results
    print(f"Password Strength: {result['strength']}")
    if result['feedback']:
        print("Suggestions to improve your password:")
        for suggestion in result['feedback']:
            print(f"- {suggestion}")
