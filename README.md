# Task Manager

A powerful, single-file task management application with real-time tracking, Excel integration, and advanced filtering capabilities.

## 📋 Overview

Task Manager is a lightweight, browser-based task management system that combines the simplicity of a single HTML file with the power of Excel data integration. It provides real-time task tracking, employee assignment, priority management, and comprehensive analytics—all without requiring a backend server or database.

### Key Features

- **📊 Excel Integration** - Import/export tasks seamlessly with Excel files
- **🕐 Real-time Tracking** - Visual current time indicator with automatic task highlighting
- **👥 Employee Management** - Assign tasks to team members with smart assignment features
- **🎯 Priority System** - Three-level priority management (High, Medium, Low)
- **✅ Status Tracking** - Four status states (Pending, In Progress, Completed, Cancelled)
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
- **Time** - Task time in h:mm AM/PM format
- **Task** - Task title/name
- **Description** - Detailed task description
- **Priority** - High, Medium, or Low
- **Assigned** - Employee name or "Everyone" for unassigned
- **Status** - Pending, In Progress, Completed, or Cancelled

> **Note:** The first 2 rows are reserved for instructions/headers and are automatically skipped during import.

#### **Employees Sheet**
Lists all team members:
- **Name** - Employee full name

#### **TaskTemplates Sheet** (Optional)
Quick task templates for frequently repeated tasks:
- **TaskName** - Template name
- **Description** - Template description

---

## 🚀 Getting Started

### Prerequisites
- Modern web browser (Chrome, Firefox, Safari, Edge)
- No installation or server required!

### Quick Start

1. **Download the files**
   ```bash
   git clone https://github.com/MohsenUSA/TaskManager.git
   cd TaskManager
   ```

2. **Open the application**
   - Double-click `TaskManager.html` to open in your default browser
   - Or right-click → Open with → [Your preferred browser]

3. **Download the template**
   - Click the **"📥 Download Template"** button in the app
   - Or use the Database.xlsx file from the repository

4. **Add your data**
   - Open Database.xlsx in Excel or any spreadsheet application
   - Add your employees to the **Employees** sheet
   - Add your tasks to the **Tasks** sheet
   - Save the file

5. **Import your data**
   - Drag and drop Database.xlsx onto the application
   - Or click the file upload area and select your file
   - Tasks will load automatically!

---

## 📖 How to Use

### Adding Tasks

**Method 1: Import from Excel**
1. Open Database.xlsx in Excel
2. Fill in task details in the Tasks sheet
3. Drag and drop the file into the application

**Method 2: Edit Exported File**
1. Click **"📊 Export to Excel"** to download current tasks
2. Edit the exported file
3. Re-import the modified file

### Managing Tasks

#### **Assign Tasks**
- Click on "Everyone ➡️" badge on any unassigned task
- Select an employee from the popup list
- Task automatically updates with assignment

#### **Change Status**
- Click on the status badge (Pending, In Progress, etc.)
- Select new status from dropdown
- Status updates immediately

#### **Filter Tasks**
1. Click **"🔍 Search"** button
2. Enter filter criteria:
   - **Employee name** - Show tasks for specific person
   - **Status** - Filter by Pending, In Progress, Completed, Cancelled
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
- Tasks by status (Pending, In Progress, Completed, Cancelled)
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
- ✅ Use consistent time format (h:mm AM/PM)
- ⚠️ Don't delete sheet names (Tasks, Employees, TaskTemplates)
- ⚠️ Don't modify column headers in the Tasks sheet

### Task Assignment
- Use "Everyone" for tasks that can be picked up by anyone
- Assign specific names for dedicated responsibilities
- Click "Everyone ➡️" to quickly reassign tasks

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

Contributions are welcome! Feel free to:
- Report bugs via GitHub Issues
- Suggest features
- Submit pull requests
- Improve documentation

---

## 📝 License

This project is open source and available under the MIT License.

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
3. Open an issue on GitHub
4. Include browser version and error details

---

**Made with ❤️ for efficient task management**
**Changes to locked cells might make Database unreadable by HTML file**
**In case you want to modify them the password is "DROWSSAP"**
