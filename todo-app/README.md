# ✓ Todo App

A simple, elegant command-line to-do list application with persistent local storage and intuitive task management.

## Features

✨ **Core Functionality**
- ✅ Create, read, update, and delete tasks
- 📝 Mark tasks as complete/incomplete
- 🔍 Filter tasks by status (all, active, completed)
- 💾 Persistent local storage (JSON file)
- 🎨 Clean terminal UI with status indicators

✨ **Advanced Features**
- 🏷️ Categorize tasks with tags
- 🔔 Set priority levels (Low, Medium, High)
- 📅 Add due dates to tasks
- 🔎 Search and filter by multiple criteria
- 📊 Task statistics and summaries
- ⏰ Auto-save on every operation

## Installation

```bash
cd todo-app
pip install -r requirements.txt
```

## Quick Start

```bash
# Run the interactive menu
python app.py

# Or import as a module
from todo_manager import TodoManager
manager = TodoManager()
manager.add_task("Buy groceries", priority="High", due_date="2026-05-20")
manager.list_tasks()
```

## Usage

### Interactive Menu

```
====== TODO APP ======
1. Add Task
2. View All Tasks
3. View Active Tasks
4. View Completed Tasks
5. Mark Task Complete
6. Mark Task Incomplete
7. Delete Task
8. Search Tasks
9. Task Statistics
10. Exit

Select option: _
```

### Example Commands

```python
from todo_manager import TodoManager

manager = TodoManager()

# Add tasks
manager.add_task("Learn Python", priority="High", due_date="2026-06-01")
manager.add_task("Buy groceries", tags=["shopping", "urgent"])
manager.add_task("Exercise", priority="Medium")

# List tasks
manager.list_tasks()  # All tasks
manager.list_tasks(status="active")
manager.list_tasks(status="completed")

# Search
manager.search("python")
manager.filter_by_tag("shopping")
manager.filter_by_priority("High")

# Update tasks
manager.complete_task(1)
manager.incomplete_task(1)
manager.update_task(1, title="Learn Python Advanced")

# Analytics
stats = manager.get_statistics()
print(f"Total: {stats['total']}, Completed: {stats['completed']}")

# Delete
manager.delete_task(1)
```

## File Structure

```
todo-app/
├── README.md                    # This file
├── requirements.txt             # Dependencies
├── app.py                       # Interactive CLI application
├── todo_manager.py              # Core task manager logic
├── storage.py                   # Local storage (JSON)
├── tasks.json                   # Auto-generated task database
└── tests/
    └── test_todo_manager.py     # Unit tests
```

## Data Storage

Tasks are stored in `tasks.json` with the following structure:

```json
{
  "tasks": [
    {
      "id": 1,
      "title": "Buy groceries",
      "description": "Milk, eggs, bread",
      "completed": false,
      "priority": "High",
      "due_date": "2026-05-20",
      "tags": ["shopping", "urgent"],
      "created_at": "2026-05-16T10:30:00",
      "updated_at": "2026-05-16T10:30:00"
    }
  ],
  "next_id": 2
}
```

## API Reference

### TodoManager Class

#### Methods

**`add_task(title, description="", priority="Medium", tags=None, due_date=None)`**
- Creates a new task
- Returns: Task ID

**`list_tasks(status=None)`**
- Lists tasks filtered by status (all, active, completed)
- Returns: List of tasks

**`complete_task(task_id)`**
- Marks task as completed
- Returns: Updated task

**`incomplete_task(task_id)`**
- Marks task as incomplete
- Returns: Updated task

**`update_task(task_id, **kwargs)`**
- Updates task fields
- Returns: Updated task

**`delete_task(task_id)`**
- Removes task from storage
- Returns: True if successful

**`search(query)`**
- Searches task titles and descriptions
- Returns: List of matching tasks

**`filter_by_tag(tag)`**
- Filters tasks by tag
- Returns: List of matching tasks

**`filter_by_priority(priority)`**
- Filters tasks by priority level
- Returns: List of matching tasks

**`get_statistics()`**
- Returns task statistics
- Returns: Dictionary with counts

## Testing

```bash
cd tests
pytest test_todo_manager.py -v
```

## Examples

### Example 1: Daily Checklist

```python
from todo_manager import TodoManager

manager = TodoManager()

tasks = [
    ("Morning workout", "Medium", "2026-05-16"),
    ("Code review", "High", "2026-05-16"),
    ("Lunch meeting", "High", "2026-05-16"),
    ("Email responses", "Low", "2026-05-16"),
]

for title, priority, due_date in tasks:
    manager.add_task(title, priority=priority, due_date=due_date)

print("Today's Tasks:")
manager.list_tasks(status="active")
```

### Example 2: Project Management

```python
manager = TodoManager()

# Project: Website Redesign
manager.add_task(
    "Design mockups",
    priority="High",
    tags=["website", "design"],
    due_date="2026-05-20"
)
manager.add_task(
    "Frontend implementation",
    priority="High",
    tags=["website", "frontend"],
    due_date="2026-05-25"
)
manager.add_task(
    "Backend API",
    priority="High",
    tags=["website", "backend"],
    due_date="2026-05-27"
)

# View project tasks
project_tasks = manager.filter_by_tag("website")
print(f"Website tasks: {len(project_tasks)}")
```

### Example 3: Smart Filtering

```python
# High-priority tasks due soon
high_priority = manager.filter_by_priority("High")
active = [t for t in high_priority if not t["completed"]]

# Tasks by multiple tags
shopping_urgent = [t for t in manager.filter_by_tag("shopping")
                   if "urgent" in t["tags"]]

# Statistics dashboard
stats = manager.get_statistics()
completion_rate = (stats["completed"] / stats["total"] * 100)
print(f"Completion Rate: {completion_rate:.1f}%")
```

## License

MIT License - See LICENSE file

## Author

High-grandmaster-watcher
