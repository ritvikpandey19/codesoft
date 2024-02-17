import os

class TodoList:
    tasks = []
    filename = "todo_list.txt"
    
    if os.path.exists(filename):
        with open(filename, 'r') as file:
            tasks = [line.strip() for line in file]

    @classmethod
    def save_tasks(cls):
        with open(cls.filename, 'w') as file:
            for task in cls.tasks:
                file.write(task + '\n')

todo_list = TodoList

while True:
    print("\nOptions:")
    print("1. Display Tasks")
    print("2. Add Task")
    print("3. Remove Task")
    print("4. Quit")

    choice = input("Enter your choice (1/2/3/4): ")

    if choice == '1':
        if not todo_list.tasks:
            print("No tasks in the to-do list.")
        else:
            print("To-Do List:")
            for index, task in enumerate(todo_list.tasks, start=1):
                print(f"{index}. {task}")
    elif choice == '2':
        task = input("Enter the task to add: ")
        todo_list.tasks.append(task)
        print(f"Task '{task}' added to the to-do list.")
        todo_list.save_tasks()
    elif choice == '3':
        task_number = input("Enter the task number to remove: ")
        try:
            task_number = int(task_number)
            if 1 <= task_number <= len(todo_list.tasks):
                removed_task = todo_list.tasks.pop(task_number - 1)
                print(f"Task '{removed_task}' removed from the to-do list.")
                todo_list.save_tasks()
            else:
                print("Invalid task number.")
        except ValueError:
            print("Invalid input. Please enter a valid task number.")
    elif choice == '4':
        print("Exiting the To-Do List application. Goodbye!")
        break
    else:
        print("Invalid choice. Please enter a valid option.")
