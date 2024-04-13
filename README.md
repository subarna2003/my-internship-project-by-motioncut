def ask_question(question, options, correct_answer):
    print(question)
    for idx, option in enumerate(options, start=1):
        print(f"{idx}. {option}")
    
    user_answer = input("Enter your answer (1-4): ")
    if user_answer.isdigit() and 1 <= int(user_answer) <= len(options):
        user_answer_idx = int(user_answer) - 1
        if options[user_answer_idx] == correct_answer:
            return True
    return False

def run_quiz(questions):
    score = 0
    for question, options, correct_answer in questions:
        if ask_question(question, options, correct_answer):
            score += 1
            print("Correct!")
        else:
            print(f"Incorrect. The correct answer is: {correct_answer}")
        print()

    return score

def main():
    questions = [
        ("What is the capital of INDIA?", ["Paris", "Berlin", "Delhi", "Madrid"], "Delhi"),
        ("Which planet is known as the Red Planet?", ["Mars", "Jupiter", "Saturn", "Earth"], "Mars"),
        ("Who wrote 'Romeo and Juliet'?", ["Shakespeare", "Dickens", "Twain", "Austen"], "Shakespeare"),
("Name the country which has no capital?", ["Usa", "Maldives", "Twain", "Nauru"], "Nauru"),
("Victoria Memorial is situated in which city of India?", ["Kashmir", "Pune", "Puri", "Kolkata"], "Kolkata"),
    ]

    print("Welcome to the Basic Quiz Game!")
    print("You will be asked a series of questions. Enter the number corresponding to your answer.")

    score = run_quiz(questions)

    print(f"Quiz completed! Your final score is: {score}")

if __name__ == "__main__":
    main()
