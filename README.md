# -AI-
スマートエデュケーションは、生成型AIと大規模言語モデルを活用して、学習者一人一人のニーズや習熟度に合わせた学習教材や課題を生成し、効果的な学習を支援します。
from random import randint, choice

# Simulated AI model for generating personalized content
def generate_math_problem(level):
    if level == 'beginner':
        operation = choice(['+', '-'])
        num1 = randint(1, 10)
        num2 = randint(1, 10)
        problem = f"What is {num1} {operation} {num2}?"
    elif level == 'intermediate':
        operation = choice(['*', '/'])
        num1 = randint(1, 10)
        num2 = randint(1, 10) if operation == '*' else randint(1, 10) * num1
        problem = f"What is {num1} {operation} {num2}?"
    else:  # advanced
        num1 = randint(1, 100)
        num2 = randint(1, 100)
        problem = f"What is {num1} * {num2} + {randint(1, 100)}?"
    
    return problem

# Example function to adapt learning content to the student
def adapt_learning_content(student):
    # Simulate determining the student's proficiency level
    level = student['proficiency_level']
    # Generate a personalized math problem based on the student's level
    personalized_problem = generate_math_problem(level)
    print(f"Personalized math problem for {student['name']} ({level}): {personalized_problem}")

# Example students
students = [
    {'name': 'Alice', 'proficiency_level': 'beginner'},
    {'name': 'Bob', 'proficiency_level': 'intermediate'},
    {'name': 'Charlie', 'proficiency_level': 'advanced'},
]

# Generate personalized content for each student
for student in students:
    adapt_learning_content(student)
