# Task Manager

A powerful, single-file task management application with real-time tracking, Excel integration, and advanced filtering capabilities.

## 📋 Overview

Task Manager is a lightweight, browser-based task management system that combines the simplicity of a single HTML file with the power of Excel data integration. It provides real-time task tracking, employee assignment, priority management, and comprehensive analytics—all without requiring a backend server or database.

### Key Features

- **📊 Excel Integration** - Import/export tasks seamlessly with Excel files
- **📅 All-Day Tasks** - Tasks without time automatically display as all-day tasks in a dedicated section
- **🕐 Real-time Tracking** - Visual current time indicator with automatic task highlighting
- **👥 Multi-User Assignment** - Assign tasks to one or multiple team members with clickable badges
- **📋 Subtasks** - Break down tasks into smaller checklist items
- **🎯 Priority System** - Three-level priority management (High, Medium, Low)
- **✅ Status Tracking** - Three status states (Pending, In Progress, Completed)
- **🔍 Advanced Search** - Filter tasks by date, status, priority, employee, or custom criteria
- **📈 Live Analytics** - Real-time metrics showing priority distribution, status breakdown, and employee workload
- **💾 Auto-save** - Automatic local storage persistence
- **🎨 Customizable Animations** - Configurable heartbeat effects for time indicators
- **📱 Responsive Design** - Works seamlessly on desktop and mobile devices

---

## 🗂️ Project Structure

### 1. **TaskManager.html**
The main application file containing:
- Complete UI/UX implementation
- Task rendering and management logic
- Excel file reading/writing functionality
- Real-time clock and time indicator system
- Search and filter engine
- Analytics and metrics dashboard
- Local storage management

### 2. **Database.xlsx**
The Excel template/database file with three sheets:

#### **Tasks Sheet**
Contains all task data with the following columns:
- **Date** - Task date in MM-DD-YYYY format
- **Time** - Task time in h:mm AM/PM format (leave blank for all-day tasks)
- **Task** - Task title/name
- **Description** - Detailed task description
- **Priority** - High, Medium, or Low
- **Assigned** - Employee name(s), comma-separated for multiple (e.g., "John, Sarah, Mike")
- **Status** - Pending, In Progress, or Completed
- **Subtasks** - Checklist items, one per line (use Alt+Enter for new lines in Excel)

> **Note:** The first 3 rows are reserved for instructions/headers and are automatically skipped during import. Tasks should be entered starting from Row 4.

#### ⚠️ Important: Date & Time Behavior

Understanding how Date and Time combinations work:

| Date | Time | Result |
|------|------|--------|
| ✅ Has date | ✅ Has time | Timed task for that specific date |
| ❌ No date | ✅ Has time | **Everyday** timed task (appears on ALL dates) |
| ✅ Has date | ❌ No time | **All-day** task for that specific date |
| ❌ No date | ❌ No time | **All-day** task for **every** date (always visible) |

#### 📥 Default Values on Import

When importing from Excel, missing fields are automatically filled with sensible defaults:

| Field | Default Value | Notes |
|-------|---------------|-------|
| **Date** | Everyday | Task appears on all dates (🔄 icon shown) |
| **Time** | All Day | Task appears in sticky blue section at top |
| **Priority** | Low | Green priority badge |
| **Assigned** | Everyone | Can be reassigned by clicking the badge |
| **Status** | Pending | Yellow status badge |

#### **Employees Sheet**
Lists all team members:
- **Name** (Column A) - Employee full name
- **Role** (Column B) - Optional role/title

> **Important:** "Everyone" must remain in Row 2 (mandatory). Add employee names starting from Row 3.

#### **TaskTemplates Sheet** (Optional)
Quick task templates for frequently repeated tasks:
- **TaskName** - Template name
- **Description** - Template description

---

## 🚀 Getting Started

### Prerequisites
- Modern web browser (Chrome 90+, Firefox 88+, Safari 14+, or Edge 90+)
- Excel, Google Sheets, or any spreadsheet application
- No installation, server, or internet connection required!

### Quick Start

1. **Open the application**
   - Double-click `TaskManager.html` to launch in your browser
   - The app works 100% offline - no server needed

2. **Get the database template**
   - Click **"📥 Download Template"** button in the app
   - Or use the included `Database.xlsx` file from the repository

3. **Set up your data** (in Database.xlsx)
   - **Employees sheet**: Add your team members starting from Row 3 (Row 2 "Everyone" is mandatory)
   - **Tasks sheet**: Add tasks starting from Row 4 with the following:
     - **Date**: Optional (MM-DD-YYYY format) - leave blank for everyday tasks
     - **Time**: Optional (h:mm AM/PM format) - leave blank for all-day tasks
     - **Task**: Task title/name
     - **Priority**: Optional - defaults to "Low" (High, Medium, or Low)
     - **Status**: Optional - defaults to "Pending" (Pending, In Progress, or Completed)
     - **Assigned**: Optional - defaults to "Everyone" (comma-separated for multiple: "John, Sarah")
     - **Description**: Optional details
     - **Subtasks**: Optional - checklist items (use Alt+Enter for new lines in cell)

4. **Import your tasks**
   - For a fresh start, click "Clear Data" first to clear any cached data, then refresh the page
   - Drag and drop `Database.xlsx` into the upload area
   - Or click the upload area to browse and select the file
   - Tasks load instantly and save to your browser automatically

### What Happens Next

✅ **All-day tasks** (no time specified) appear in a sticky blue section at the top
✅ **Everyday tasks** (no date specified) appear on ALL dates with a 🔄 icon
✅ **Timed tasks** display below, sorted chronologically
✅ **Current time indicator** shows your position in the day (red line)
✅ **Real-time updates** - clock updates every second
✅ **Auto-save** - all changes saved to browser localStorage
✅ **Export anytime** - click "📊 Export to Excel" to download your updated tasks

---

## 📖 How to Use

### Adding Tasks

**Method 1: Import from Excel**
1. Open Database.xlsx in Excel
2. Fill in task details in the Tasks sheet (starting from Row 4)
3. Drag and drop the file into the application

**Method 2: Edit Exported File**
1. Click **"📊 Export to Excel"** to download current tasks
2. Edit the exported file
3. Re-import the modified file

### Managing Tasks

#### **All-Day Tasks**
- Leave the Time column blank in Excel to create all-day tasks
- All-day tasks appear in a blue-bordered section at the top
- Displayed vertically (same layout as timed tasks)
- Shows "📅 All Day" badge instead of time
- Automatically sorted by priority: High → Medium → Low
- Perfect for deadlines, reminders, or tasks without specific times

#### **Assign Tasks**
- Click on any assignee badge (e.g., "Everyone", "John", etc.)
- Multi-select modal opens with all employees
- Click to select/deselect multiple assignees
- Selected employees highlighted in purple
- Click "Confirm" to save changes
- Multiple assignees display as: 👥 [John] [Sarah] [Mike]

#### **Subtasks**
- Add subtasks in Excel using the Subtasks column
- Use Alt+Enter (Windows) or Ctrl+Option+Enter (Mac) for new lines
- Subtasks display as a checklist within the task card:
  ```
  📋 Subtasks:
    ○ Review agenda
    ○ Take notes
    ○ Assign action items
  ```
- Subtasks are informational only (no status tracking)

#### **Change Status**
- Click on the status badge (Pending, In Progress, etc.)
- Select new status from dropdown
- Status updates immediately

#### **Filter Tasks**
1. Click **"🔍 Search"** button
2. Enter filter criteria:
   - **Employee name** - Show tasks for specific person
   - **Status** - Filter by Pending, In Progress, or Completed
   - **Priority** - Filter by High, Medium, Low
   - **Date** - Select specific date from date picker
3. Click **"Search"** to apply
4. Click **"Reset"** to show all tasks

### Navigation

#### **Current Time Indicator**
- Red line shows current time on today's tasks
- Red circle marks the current position
- Current task is highlighted with red border

#### **Floating Clock Button (🕐)**
- Click to scroll to current time indicator
- Changes to ⬆ when at current time
- Click ⬆ to return to top
- Auto-follows current time as it updates

#### **Date Navigation**
- Use date chips at top to quickly jump between task dates
- Click any date to filter tasks for that day
- Today's date is highlighted

---

## ⚙️ Configuration

### Animation Settings

Located at the top of the `<script>` section in TaskManager.html:

```javascript
// ============================================
// ANIMATION SETTINGS (Easy Configuration)
// ============================================
const ENABLE_ANIMATIONS = true;        // Set to false to disable all animations
const ANIMATION_INTERVAL = '10s';      // Animation cycle duration (e.g., '2s', '5s', '10s')
// ============================================
```

**Controls:**
- Current time indicator line pulse
- Red circle indicator pulse
- Current task card highlight

**To disable animations:**
```javascript
const ENABLE_ANIMATIONS = false;
```

**To change animation speed:**
```javascript
const ANIMATION_INTERVAL = '5s';  // Faster
const ANIMATION_INTERVAL = '30s'; // Slower
```

---

## 📊 Analytics Dashboard

The application provides real-time metrics:

### Priority Breakdown
- Visual count of High, Medium, and Low priority tasks
- Color-coded cards (Red, Orange, Green)

### Status Breakdown
- Tasks by status (Pending, In Progress, Completed)
- Percentage distribution

### Tasks by Employee
- Workload distribution across team members
- Sorted by task count

### Priority × Status Matrix
- Cross-tabulated view showing task distribution
- Helps identify bottlenecks (e.g., High priority tasks stuck in Pending)

---

## 💡 Tips & Best Practices

### Excel File Management
- ✅ Keep the Database.xlsx file as your master copy
- ✅ Export regularly to back up your tasks
- ✅ Use consistent date format (MM-DD-YYYY)
- ✅ Use consistent time format (h:mm AM/PM for timed tasks)
- ✅ Leave Date column blank for everyday tasks (appears on all dates)
- ✅ Leave Time column blank for all-day tasks
- ✅ Missing fields auto-fill with defaults (Priority→Low, Status→Pending, Assigned→Everyone)
- ⚠️ Don't delete sheet names (Tasks, Employees, TaskTemplates)
- ⚠️ Don't modify column headers in the Tasks sheet
- ⚠️ Don't remove "Everyone" from Row 2 in the Employees sheet (mandatory)

### All-Day Tasks Best Practices
- Use all-day tasks for deadlines without specific times
- Leave Time blank for full-day events or reminders
- High priority all-day tasks appear first in the sticky section
- All-day tasks won't trigger current/past time indicators
- Perfect for daily goals, milestones, or flexible deadlines

### Everyday Tasks Best Practices
- Leave Date blank to create tasks that appear on ALL dates
- Everyday tasks display a 🔄 icon to indicate they're recurring
- Combine with Time for daily scheduled reminders (e.g., "9:00 AM Daily Standup")
- Combine without Time for persistent all-day reminders
- Perfect for daily routines, recurring meetings, or standing reminders

### Task Assignment
- Use "Everyone" for tasks that can be picked up by anyone
- Assign specific names for dedicated responsibilities
- Click any assignee badge to open the multi-select modal
- Assign multiple people: "John, Sarah, Mike" in Excel or via the modal
- Selecting "Everyone" clears individual assignments
- 👤 icon = single assignee, 👥 icon = multiple assignees

### Subtasks Best Practices
- Use subtasks to break complex tasks into smaller steps
- Enter each subtask on a new line (Alt+Enter in Excel)
- Keep subtask descriptions concise
- Subtasks are informational - no separate status tracking
- Perfect for checklists, step-by-step procedures, or action items

### Performance
- The app updates every second to keep time indicators accurate
- Data is automatically saved to browser local storage
- Clear data with **"🗑️ Clear Data"** button if needed

### Mobile Usage
- Responsive design works on all screen sizes
- Touch gestures supported for scrolling and interactions
- Tooltips hidden on mobile for cleaner interface

---

## 🔒 Data Privacy

- **100% Local** - All data stored in your browser (localStorage)
- **No Server** - No data sent to external servers
- **No Tracking** - No analytics or tracking scripts
- **Offline Capable** - Works without internet connection
- **Your Data** - Excel files stay on your device

---

## 🛠️ Technical Details

### Built With
- Pure HTML5, CSS3, and JavaScript (ES6+)
- [ExcelJS](https://github.com/exceljs/exceljs) - Excel file processing
- [SheetJS](https://github.com/SheetJS/sheetjs) - Excel file parsing
- LocalStorage API - Data persistence

### Browser Compatibility
- Chrome/Edge 90+
- Firefox 88+
- Safari 14+
- Opera 76+

### File Size
- TaskManager.html: ~140KB (uncompressed)
- Database.xlsx: ~15KB

---

## 🤝 Contributing

Contributions are welcome! Feel free to report bugs via GitHub Issues or on Twitter/X

---

## 📝 License

This project is open source and available under the MIT License for any lawful use.

---

## 👤 Author

**Mohsen**
- GitHub: [@MohsenUSA](https://github.com/MohsenUSA)

---

## 🙏 Acknowledgments

- ExcelJS library for Excel file manipulation
- SheetJS for Excel parsing capabilities
- The open-source community for inspiration

---

## 📞 Support

If you encounter issues or have questions:
1. Check this README for guidance
2. Review the Getting Started section
3. [Download SOP](https://github.com/MohsenUSA/TaskManager/blob/0c1e00f7ee4f9309c10a39e2daa387037681d955/SOP.md) - Standard Operating Procedures for detailed usage instructions
4. Need help or have suggestions or feedback? find me on Twitter/X : [@XPRODUCTIVITY](https://x.com/xproductivity)

---

**Made with ❤️ for efficient task management**

**Changes to locked cells might make Database unreadable by HTML file**

**In case you want to modify them the password is "DROWSSAP"**
