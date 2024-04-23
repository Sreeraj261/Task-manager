class Task:
    def __init__(self, task_id, title, description, priority, status):
        self.task_id = task_id
        self.title = title
        self.description = description
        self.priority = priority
        self.status = status

    def __str__(self):
        return f"Task ID: {self.task_id}\nTitle: {self.title}\nDescription: {self.description}\nPriority: {self.priority}\nStatus: {self.status}"

class TaskManager:
    def __init__(self):
        self.tasks = []

    def add_task(self, task):
        self.tasks.append(task)

    def edit_task(self, task_id, title, description, priority, status):
        task = self.get_task_by_id(task_id)
        if task:
            task.title = title
            task.description = description
            task.priority = priority
            task.status = status
            print("Task edited successfully.")
        else:
            print("Task ID not found.")

    def delete_task(self, task_id):
        task = self.get_task_by_id(task_id)
        if task:
            self.tasks.remove(task)
            print("Task deleted successfully.")
        else:
            print("Task ID not found.")

    def get_task_by_id(self, task_id):
        for task in self.tasks:
            if task.task_id == task_id:
                return task
        return None

    def view_all_tasks(self):
        if not self.tasks:
            print("No tasks.")
        else:
            for task in self.tasks:
                print(task)

    def filter_tasks_by_priority(self, priority):
        filtered_tasks = [task for task in self.tasks if task.priority == priority]
        if not filtered_tasks:
            print("No tasks with the specified priority.")
        else:
            for task in filtered_tasks:
                print(task)

def main():
    task_manager = TaskManager()

    while True:
        print("\nTask Manager Menu:")
        print("1. Add Task")
        print("2. Edit Task")
        print("3. Delete Task")
        print("4. View All Tasks")
        print("5. Filter Tasks by Priority")
        print("6. Exit")

        choice = input("Enter your choice: ")

        if choice == "1":
            task_id = int(input("Enter Task ID: "))
            title = input("Enter Title: ")
            description = input("Enter Description: ")
            priority = input("Enter Priority (High/Medium/Low): ")
            status = input("Enter Status (Pending/In Progress/Completed): ")
            task_manager.add_task(Task(task_id, title, description, priority, status))
            print("Task added successfully!")
        elif choice == "2":
            task_id = int(input("Enter Task ID to edit: "))
            title = input("Enter New Title: ")
            description = input("Enter New Description: ")
            priority = input("Enter New Priority (High/Medium/Low): ")
            status = input("Enter New Status (Pending/In Progress/Completed): ")
            task_manager.edit_task(task_id, title, description, priority, status)
        elif choice == "3":
            task_id = int(input("Enter Task ID to delete: "))
            task_manager.delete_task(task_id)
        elif choice == "4":
            task_manager.view_all_tasks()
        elif choice == "5":
            priority = input("Enter Priority to filter tasks (High/Medium/Low): ")
            task_manager.filter_tasks_by_priority(priority)
        elif choice == "6":
            print("Exiting...")
            break
        else:
            print("Invalid choice. Please enter a number between 1 and 6.")

if __name__ == "__main__":
    main()
