# codsoft-task-3
import tkinter as tk
import random

def check_answer():
    answer = entry.get()
    if answer.lower() == correct_answer.lower():
        result_label.config(text="Correct!", fg="green")
    else:
        result_label.config(text="Incorrect!", fg="red")

def next_question():
    global correct_answer
    correct_answer = random.choice(questions)
    question_label.config(text=correct_answer)
    entry.delete(0, tk.END)
    result_label.config(text="")

def main():
    global questions, correct_answer
    window = tk.Tk()
    window.title("Quiz Game by anshika")
    window.geometry("500x500")

    questions = ["What is the capital of india?", "Who is the president of india?", "Who is the prime minister of india ?"]
    answers = ["New Delhi", "Druopati murmur", "Narendra modi"]
    correct_answer = random.choice(questions)

    question_label = tk.Label(window, text=correct_answer, font=("Open Sans", 40))
    question_label.pack(pady=20)
    
    entry = tk.Entry(window, font=("Open Sans", 40))
    entry.pack(pady=40)

    check_button = tk.Button(window, text="Check", command=check_answer)
    check_button.pack(pady=20)

    next_button = tk.Button(window, text="Next Question", command=next_question)
    next_button.pack(pady=20)

    result_label = tk.Label(window, text="", font=("Open Sans", 40)
    result_label.pack(pady=5)

    window.mainloop()

if __name__ == "__main__":
    main()
