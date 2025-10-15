# 🚀 Advanced Task Manager Pro

A feature-rich, cross-platform task management application built with Python and Tkinter. Manage your tasks with priorities, categories, due dates, analytics, and CSV import/export capabilities.



## ✨ Features

- **📝 Task Management**: Create, edit, delete, and complete tasks
- **🔥 Priority Levels**: High, Medium, Low with visual indicators
- **📂 Categories**: Organize tasks by Work, Personal, Study, Health, etc.
- **📅 Due Dates**: Set deadlines and track overdue tasks
- **🔍 Filtering**: Filter by priority, status, or overdue tasks
- **📊 Analytics Dashboard**: Completion rates, priority breakdowns, productivity insights
- **📤 CSV Import/Export**: Backup and restore your task data
- **🔔 Notifications**: Background reminders for upcoming deadlines
- **⏱️ Time Tracking**: Estimate and track time spent on tasks
- **💾 SQLite Database**: Persistent storage with automatic schema management
- **🎨 Modern UI**: Clean interface with emojis and intuitive controls

## 🛠️ Installation

### Prerequisites
- Python 3.7 or higher
- pip (Python package manager)

### Quick Start
1. **Clone the repository**:
   ```bash
   git clone https://github.com/yourusername/advanced-task-manager-pro.git
   cd advanced-task-manager-pro
   ```

2. **Run the application**:
   ```bash
   python main.py
   ```

3. **Optional: Install additional dependencies** (for enhanced features):
   ```bash
   pip install tkcalendar plyer
   ```
   - `tkcalendar`: For date picker widgets
   - `plyer`: For desktop notifications

The application will automatically create a SQLite database (`tasks_advanced.db`) in the application directory.

## 🚀 Usage

### Adding Tasks
1. Fill in the task details in the "Add New Task" section:
   - **Title**: Required task name
   - **Description**: Optional details
   - **Priority**: High/Medium/Low
   - **Category**: Work/Personal/Study/etc.
   - **Due Date**: Format `YYYY-MM-DD`
   - **Estimated Hours**: Optional time estimate

2. Click **"➕ Add Task"** to save

### Managing Tasks
- **Select** a task from the list to edit it
- **✏️ Update**: Modify selected task details
- **✅ Complete**: Mark task as done
- **🗑️ Delete**: Remove selected task (with confirmation)

### Filtering & Searching
- Use the filter dropdown to view:
  - All tasks
  - Specific priorities
  - Pending/Completed tasks
  - Overdue tasks
- Click **"Apply"** to filter results

### Analytics
Click **"📊 Analytics"** to view:
- Task completion statistics
- Priority and category breakdowns
- Productivity insights and tips
- Visual progress indicators

### Data Management
- **📤 Export CSV**: Save tasks to CSV file
- **📥 Import CSV**: Restore tasks from CSV backup

## 🎯 Task Workflow

1. **Create** tasks with priorities and deadlines
2. **Organize** by categories and due dates
3. **Track** progress with status updates
4. **Monitor** overdue tasks via filters
5. **Analyze** productivity with the dashboard
6. **Backup** data regularly using CSV export

## 🗄️ Database Schema

The application uses SQLite with the following table structure:

```sql
CREATE TABLE tasks (
    id INTEGER PRIMARY KEY AUTOINCREMENT,
    title TEXT NOT NULL,
    description TEXT,
    priority TEXT DEFAULT 'Medium',
    due_date TEXT,
    category TEXT DEFAULT 'General',
    status TEXT DEFAULT 'Pending',
    created_date TEXT,
    completed_date TEXT,
    estimated_time INTEGER DEFAULT 0,
    actual_time INTEGER DEFAULT 0,
    tags TEXT,
    reminder_sent BOOLEAN DEFAULT 0
);
```

## 🔧 Configuration

### Date Format
- Due dates must be in `YYYY-MM-DD` format (e.g., `2024-12-31`)
- The app validates dates and shows warnings for past dates

### Database Location
- Database file: `tasks_advanced.db` (created automatically)
- Stored in the application directory
- **Backup regularly** using CSV export

### Notifications
- Background thread checks for due tasks every hour
- Console notifications for tasks due tomorrow
- Enhanced notifications available with `plyer` dependency

## 📁 File Structure

```
advanced-task-manager-pro/
├── main.py                 # Main application file
├── tasks_advanced.db       # SQLite database (auto-created)
├── screenshots/            # Screenshots for documentation
├── README.md              # This file
├── LICENSE                # MIT License
└── requirements.txt       # Optional dependencies
```

## 🛠️ Customization

### Adding Categories
Modify the `category_combo` values in `create_widgets()`:
```python
self.category_combo = ttk.Combobox(
    input_frame, 
    values=["Work", "Personal", "Study", "Health", "Shopping", "Custom Category"],
    width=22
)
```

### Priority Colors
Update priority display logic in `load_tasks()`:
```python
priority_display = {
    "High": "🔴 High",      # Red
    "Medium": "🟡 Medium",  # Yellow
    "Low": "🟢 Low"         # Green
}[priority]
```

### Custom Filters
Add new filter options in the `filter_combo`:
```python
values=["All", "High Priority", "Custom Filter", "Overdue"]
```

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

### Development Setup
```bash
# Install development dependencies
pip install -r requirements.txt

# Run with debugging
python -m pdb main.py

# Run tests (if implemented)
python -m pytest
```

## 🐛 Troubleshooting

### Common Issues

1. **Database locked error**:
   - Close all instances of the application
   - Delete `tasks_advanced.db` to reset (⚠️ Data loss!)

2. **Date format errors**:
   - Use `YYYY-MM-DD` format exactly
   - Avoid spaces or other separators

3. **Notifications not working**:
   - Install `plyer`: `pip install plyer`
   - Check console output for reminders

4. **Import/Export issues**:
   - Ensure CSV files use UTF-8 encoding
   - Verify CSV structure matches expected columns

### Logs
Check console output for:
- Database initialization messages
- Notification reminders
- Import/export status



---

*Version 1.0.0 | Last Updated: October 2024*
