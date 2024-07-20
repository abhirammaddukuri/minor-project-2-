tasks = []

def add_task():
    task = input("Enter a new task: ")
    tasks.append(task)
    print("Task added successfully!")

def remove_task():
    while True:
        try:
            task_number = int(input("Enter the task number to remove: "))
            if task_number > 0 and task_number <= len(tasks):
                tasks.pop(task_number - 1)
                print("Task removed successfully!")
                break
            else:
                print("Invalid task number! Please try again.")
        except ValueError:
            print("Invalid input! Please enter a number.")

def mark_task_as_completed():
    while True:
        try:
            task_number = int(input("Enter the task number to mark as completed: "))
            if task_number > 0 and task_number <= len(tasks):
                tasks[task_number - 1] += " (Completed)"
                print("Task marked as completed!")
                break
            else:
                print("Invalid task number! Please try again.")
        except ValueError:
            print("Invalid input! Please enter a number.")

def display_all_tasks():
    for i, task in enumerate(tasks, start=1):
        print(f"Task {i}: {task}")

def display_incomplete_tasks():
    for i, task in enumerate(tasks, start=1):
        if "(Completed)" not in task:
            print(f"Task {i}: {task}")

while True:
    print("Welcome to the To-Do List App!")
    print("What would you like to do?")
    print("1. Add a new task")
    print("2. Remove a task")
    print("3. Mark a task as completed")
    print("4. Display all tasks")
    print("5. Display only incomplete tasks")
    print("6. Quit")
    choice = input("Enter your choice: ")
    if choice == "1":
        add_task()
    elif choice == "2":
        remove_task()
    elif choice == "3":
        mark_task_as_completed()
    elif choice == "4":
        display_all_tasks()
    elif choice == "5":
        display_incomplete_tasks()
    elif choice == "6":
        break
    else:
        print("Invalid choice!")