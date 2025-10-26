# Smart_Task-Scheduler_with_Priority_Queues
📋 Overview
Smart Task Scheduler is a sophisticated desktop application that revolutionizes task management using priority queues to automatically organize your tasks based on urgency and importance. Built with Java Swing, it features intelligent sorting, smart reminders, and a clean, professional interface.

https://via.placeholder.com/800x400/2D3748/FFFFFF?text=Smart+Task+Scheduler+Demo

✨ Features
🎯 Core Features
🤖 Smart Prioritization - Automatic task ordering using PriorityQueue algorithms

📅 Deadline Management - Visual deadline tracking with date/time precision

🔔 Smart Reminders - System tray notifications for upcoming deadlines

💾 Data Persistence - CSV-based save/load with proper escaping

🎨 Modern GUI - Clean Swing interface with intuitive controls

🔧 Advanced Capabilities
🎚️ Priority Levels - High, Medium, Low with intelligent sorting

🔍 Smart Filtering:

📅 Today's Tasks

⚡ High Priority

📅 Due This Week

⏰ Overdue Tasks

✅ Completed Tasks

🔄 Active Tasks

🔍 Real-time Search - Instant filtering by title and description

✏️ Full CRUD Operations - Add, Edit, Delete, Toggle Completion

📊 Visual Indicators - Color-coded priorities and overdue status

🚀 Quick Start
Prerequisites
Java JDK 17 or higher

Installation & Running
1. Download the Code
bash
git clone https://github.com/yourusername/smart-task-scheduler.git
cd smart-task-scheduler
2. Compile and Run
bash
# Compile all Java files
javac *.java

# Run the application
java Main
3. Or use the provided scripts:
bash
# Windows
run.bat

# Linux/macOS
chmod +x run.sh
./run.sh
🎮 Usage
Adding Tasks
Click "Add" button

Fill in task details:

Title: Task name (required)

Priority: High, Medium, or Low

Deadline: Format YYYY-MM-DD HH:MM (e.g., 2024-12-31 14:30)

Description: Optional detailed description

Click "Save" - watch it auto-sort into the right position!

Task Management
Action	How To
Edit Task	Select task → Click "Edit"
Delete Task	Select task → Click "Delete"
Toggle Completion	Select task → Click "Toggle Done"
Filter Views	Use dropdown filter for different views
Search	Type in search box for instant filtering
Priority System
🔥 High Priority: Critical tasks that need immediate attention (Red)

⚠️ Medium Priority: Important but not urgent tasks (Orange)

💤 Low Priority: Tasks that can be done when time permits (Black)

Smart Features
"Next Up" Button: Shows the highest priority task due next

Auto-refresh: Table updates instantly on any change

Overdue Highlighting: Overdue tasks shown in red bold

System Tray Reminders: Notifications for tasks due in 15 minutes

🏗️ Project Structure
text
smart-task-scheduler/
├── Main.java                 # Application entry point
├── Task.java                 # Task entity with CSV serialization
├── TaskManager.java          # Core PriorityQueue logic & filtering
├── TaskTableModel.java       # Custom table model for task display
├── MainFrame.java            # Main application window
├── TaskDialog.java           # Add/Edit task dialog
├── ReminderService.java      # Automated reminder system
├── run.bat                   # Windows launcher
└── run.sh                    # Linux/macOS launcher
🔧 Technical Implementation
Priority Queue Algorithm
java
private final Comparator<Task> priorityComparator = Comparator
    .comparing(Task::getPriority, Comparator.comparingInt(p -> {
        switch (p) {
            case HIGH: return 0;
            case MEDIUM: return 1;
            default: return 2;
        }
    }))
    .thenComparing(Task::getDeadline)
    .thenComparing(Task::getCreatedAt);
Data Persistence
CSV Format with proper escaping for special characters

Pipe-separated values with support for multi-line descriptions

Automatic encoding using UTF-8

Smart Filtering
Temporal Filters: Today, This Week, Overdue

Status Filters: Active, Completed

Priority Filters: High priority tasks

Combined Search: Text search across all filters

📸 Demo
Main Interface
https://via.placeholder.com/600x400/4A5568/FFFFFF?text=Main+Interface+with+Task+Table

Task Dialog
https://via.placeholder.com/400x300/4A5568/FFFFFF?text=Add+Edit+Task+Dialog

System Reminders
https://via.placeholder.com/400x200/4A5568/FFFFFF?text=System+Tray+Notifications

🛠️ Development
Building from Source
bash
# Compile
javac -encoding UTF-8 *.java

# Create JAR (optional)
jar cfe TaskScheduler.jar Main *.class
Code Architecture
MVC Pattern: Separation of data, view, and controller

Custom Table Model: Efficient task display with sorting

Event-Driven: Responsive UI with proper Swing threading

Service Layer: Reminder service running in background

🐛 Troubleshooting
Common Issues
"Invalid input" when adding tasks

Ensure deadline format is YYYY-MM-DD HH:MM

Title cannot be empty

Reminders not showing

Check system tray support

Ensure application has notification permissions

File save/load issues

Check file permissions in save directory

Ensure CSV files aren't open in other programs

System Requirements
Java: Version 17 or higher

Memory: 512MB RAM minimum

Storage: 10MB free space

OS: Windows 10+, macOS 10.14+, or Linux with GUI

🤝 Contributing
We welcome contributions! Please feel free to submit pull requests for:

New features

Bug fixes

UI improvements

Documentation updates

Development Setup
Fork the repository

Create a feature branch

Make your changes

Test thoroughly

Submit a pull request

📄 License
This project is licensed under the MIT License - see the LICENSE file for details.

🔮 Future Enhancements
Cloud synchronization

Recurring tasks

Task categories/tags

Mobile companion app

Advanced analytics

Email notifications

Calendar integration
