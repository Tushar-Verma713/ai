import os

TASK_FILE = "tasks.txt"

def load_tasks():
    if not os.path.exists(TASK_FILE):
        return []
    with open(TASK_FILE, "r") as f:
        return [line.strip() for line in f.readlines()]

def save_tasks(tasks):
    with open(TASK_FILE, "w") as f:
        for task in tasks:
            f.write(task + "\n")

def show_tasks(tasks):
    if not tasks:
        print("No tasks yet.")
    else:
        for i, task in enumerate(tasks, 1):
            print(f"{i}. {task}")

def main():
    tasks = load_tasks()

    while True:
        print("\n1. View Tasks\n2. Add Task\n3. Mark Task as Done\n4. Exit")
        choice = input("Choose: ")

        if choice == "1":
            show_tasks(tasks)
        elif choice == "2":
            task = input("Enter new task: ")
            tasks.append(task)
            save_tasks(tasks)
        elif choice == "3":
            show_tasks(tasks)
            num = int(input("Enter task number to mark done: "))
            if 1 <= num <= len(tasks):
                tasks.pop(num - 1)
                save_tasks(tasks)
            else:
                print("Invalid task number.")
        elif choice == "4":
            break
        else:
            print("Invalid choice.")

if __name__ == "__main__":
    main()
