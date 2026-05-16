# Getting Started with Todo App

## Quick Setup (30 seconds)

### Option 1: Pure Frontend (No backend required)
```bash
cd todo-app
open src/index.html
# Or: python -m http.server 3000 in the src folder
```

### Option 2: With Node.js Backend
```bash
cd todo-app
npm install
npm start
```

## Features Overview

### ✨ Core Features

**Task Management**
- Create tasks with title, description, priority, category, and due date
- Mark tasks as complete/incomplete
- Edit existing tasks
- Delete tasks with confirmation

**Organization**
- Filter by status (All, Active, Completed, High Priority)
- Search tasks by title or description
- Sort by date, priority, title, or creation date
- Track 4 key statistics

**Persistence**
- All tasks saved to browser localStorage
- Automatic saving on every change
- Data survives browser restart

**Data Operations**
- Export tasks as JSON file for backup
- Import tasks from previously exported JSON
- Clear all tasks with confirmation

**Customization**
- Dark/Light theme toggle
- Auto-archive completed tasks (optional)
- Notification preferences
- Custom sort preferences

---

## Usage Guide

### Creating a Task

1. **Simple Task**
   - Type task title in input field
   - Click "Add Task" button

2. **Detailed Task**
   - Click "Advanced Options" to expand
   - Fill in description, priority, category, due date
   - Click "Add Task"

### Managing Tasks

**Complete a Task**
- Click the checkbox next to the task
- Task becomes grayed out

**Edit a Task**
- Click the "✏️ Edit" button on the task
- Modify fields in the modal
- Click "Save Changes"

**Delete a Task**
- Click the "🗑️ Delete" button
- Confirm the deletion

### Organizing Tasks

**Search**
- Type in the search box to filter by title or description
- Real-time filtering as you type

**Filter**
- Use filter buttons: All, Active, Completed, High Priority
- Only one filter active at a time

**Sort**
- Use the sort dropdown: Date, Priority, Title, Created
- Default sort is by due date

### Managing Data

**Export Tasks**
1. Click Settings (⚙️)
2. Click "📥 Export Tasks"
3. JSON file downloads to your computer

**Import Tasks**
1. Click Settings (⚙️)
2. Click "📤 Import Tasks"
3. Select a previously exported JSON file
4. Confirm to merge with existing tasks

**Clear All**
1. Click Settings (⚙️)
2. Click "🗑️ Clear All Tasks"
3. Double-confirm (cannot be undone!)

---

## Priority Levels

| Level | Color | Use Case |
|-------|-------|----------|
| 🔴 High | Red | Urgent tasks |
| 🟡 Medium | Yellow | Standard priority |
| 🟢 Low | Green | Non-urgent |

## Categories

Default categories:
- 📋 Work
- 👤 Personal
- 🛒 Shopping
- 📚 Learning
- 💪 Health

---

## Tips & Tricks

### Power User Tips

1. **Bulk Export/Import**
   - Export all tasks regularly for backup
   - Import from backup if tasks are lost

2. **Filtering Workflow**
   - Use High Priority filter to focus on urgent tasks
   - Use Active filter to see pending work
   - Use Completed filter to see what you've done

3. **Due Dates**
   - Tasks are sorted by due date by default
   - Overdue tasks show a warning
   - Set dates to organize workflow

4. **Search Performance**
   - Search works on title and description
   - Use keywords for quick filtering
   - Great for finding tasks later

5. **Theme Usage**
   - Use dark theme in low-light environments
   - Light theme for printing
   - Preference saves automatically

### Keyboard Shortcuts (Coming Soon)
- `Ctrl + N` or `Cmd + N` - New task
- `Ctrl + /` or `Cmd + /` - Focus search
- `Esc` - Close modals

---

## Troubleshooting

### Tasks Not Saving

**Problem**: Tasks disappear after closing browser

**Solution**:
- Check if localStorage is enabled
- Go to Settings > browser privacy
- Allow localStorage for this website
- Not supported in private/incognito mode

### Too Much Storage Used

**Problem**: "Storage quota exceeded" message

**Solution**:
- Export tasks as backup
- Delete completed old tasks
- Clear browser cache/cookies
- Archive completed tasks

### Lost Data

**Problem**: All tasks are gone

**Solution**:
- Check if you have a backup JSON file
- Import the backup file
- If no backup, data cannot be recovered

### Theme Not Saving

**Problem**: Dark mode resets after reload

**Solution**:
- Check localStorage is enabled
- Clear browser cache
- Reload the page
- Theme preference should save automatically

---

## Data Storage Details

### Where is My Data Stored?

- **Location**: Browser's localStorage
- **Size Limit**: ~5-10MB per domain
- **Persistence**: Until cleared manually
- **Security**: Not encrypted (don't store sensitive data)
- **Privacy**: Local only (not sent to any server)

### Backup Recommendations

1. Export weekly to backup folder
2. Store backups in multiple locations
3. Include date in filename (auto-done)
4. Document important tasks separately

---

## Browser Compatibility

| Browser | Version | Support |
|---------|---------|---------|
| Chrome | Latest | ✅ Full |
| Firefox | Latest | ✅ Full |
| Safari | 11+ | ✅ Full |
| Edge | Latest | ✅ Full |
| IE11 | 11 | ⚠️ Limited |

**Not Supported:**
- Private/Incognito mode (no persistence)
- Very old browsers (<IE10)
- Some mobile browser restrictions

---

## Frequently Asked Questions

**Q: Will my tasks sync across devices?**  
A: Not automatically. Use Export/Import to move between devices.

**Q: Can I share tasks with others?**  
A: Export and share the JSON file. They can import it.

**Q: How do I delete a category?**  
A: Edit tasks in that category and change their category. Unused categories disappear.

**Q: Can I undo a deletion?**  
A: Only if you have an exported backup. Otherwise, it's permanent.

**Q: Is there a mobile app?**  
A: The web app works on mobile browsers. Check mobile optimizations.

**Q: How is data encrypted?**  
A: It's not. Don't store sensitive personal information.

---

## Advanced Usage

### Command Line (Node.js Backend)

```bash
# Development
npm run dev

# Testing
npm test
npm test -- --coverage

# Linting
npm run lint

# Format code
npm run format

# Production build
npm run build
```

### API Endpoints (If Using Backend)

**GET** `/api/tasks` - Get all tasks  
**POST** `/api/tasks` - Create task  
**PUT** `/api/tasks/:id` - Update task  
**DELETE** `/api/tasks/:id` - Delete task  
**GET** `/api/tasks/search` - Search tasks  

---

## Next Steps

1. ✅ Create your first task
2. ✅ Try different filters
3. ✅ Export your tasks as backup
4. ✅ Explore settings and preferences
5. ✅ Share feedback!

Happy task managing! 📝✨
