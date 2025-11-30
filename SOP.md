# Task Manager - Standard Operating Procedure (SOP)

**Document Version:** 1.0
**Effective Date:** November 2024
**Last Updated:** November 2024

---

## Table of Contents

1. [Purpose](#1-purpose)
2. [Scope](#2-scope)
3. [Roles and Responsibilities](#3-roles-and-responsibilities)
4. [Prerequisites](#4-prerequisites)
5. [Initial Setup](#5-initial-setup)
6. [Daily Operations](#6-daily-operations)
7. [Task Management Procedures](#7-task-management-procedures)
8. [Data Management](#8-data-management)
9. [Reporting and Analytics](#9-reporting-and-analytics)
10. [Troubleshooting](#10-troubleshooting)
11. [Maintenance](#11-maintenance)
12. [Revision History](#12-revision-history)

---

## 1. Purpose

This Standard Operating Procedure establishes consistent guidelines for using the Task Manager application to track, assign, and manage team tasks effectively.

### Objectives

- Ensure consistent task management across the organization
- Maintain accurate task tracking and status updates
- Enable effective workload distribution among team members
- Provide reliable data for performance analytics and reporting

---

## 2. Scope

This SOP applies to all personnel using the Task Manager application for:

- Daily task tracking and management
- Employee task assignment
- Status and priority management
- Task reporting and analytics
- Data import/export operations

---

## 3. Roles and Responsibilities

### 3.1 Task Manager Administrator

| Responsibility | Description |
|----------------|-------------|
| System Setup | Initial configuration and employee roster management |
| Data Management | Maintain master Database.xlsx file |
| User Training | Onboard new users to the application |
| Data Backup | Ensure regular exports and backups |
| Troubleshooting | First point of contact for issues |

### 3.2 Team Lead / Supervisor

| Responsibility | Description |
|----------------|-------------|
| Task Assignment | Assign tasks to appropriate team members |
| Priority Setting | Set and adjust task priorities |
| Status Monitoring | Review team task progress daily |
| Reporting | Generate and review analytics reports |

### 3.3 Team Member

| Responsibility | Description |
|----------------|-------------|
| Status Updates | Update task status as work progresses |
| Task Review | Review assigned tasks daily |
| Time Management | Complete tasks within scheduled timeframes |

---

## 4. Prerequisites

### 4.1 System Requirements

| Requirement | Specification |
|-------------|---------------|
| Web Browser | Chrome 90+, Firefox 88+, Safari 14+, or Edge 90+ |
| Spreadsheet Software | Microsoft Excel, Google Sheets, or compatible application |
| Storage | Minimum 50MB free disk space |
| Internet | Not required (offline capable) |

### 4.2 Required Files

| File | Purpose |
|------|---------|
| `TaskManager.html` | Main application file |
| `Database.xlsx` | Data template and storage |

---

## 5. Initial Setup

### 5.1 First-Time Application Setup

**Procedure:**

1. **Obtain Application Files**
   - Download or copy `TaskManager.html` and `Database.xlsx` to local computer
   - Store files in an accessible, backed-up location

2. **Launch Application**
   - Double-click `TaskManager.html`
   - Application opens in default web browser
   - Verify clock displays current time

3. **Verify Application Loads**
   - Confirm header shows current date and time
   - Confirm control buttons are visible (Upload, Export, Clear, Search)
   - Confirm metrics panel is accessible

### 5.2 Employee Roster Setup

**Procedure:**

1. Open `Database.xlsx` in spreadsheet application
2. Navigate to **Employees** sheet
3. Clear sample data, if present (Everyone in row 2 is not removable and mandatory)
4. Enter employee names in Column A, starting from Row 3
   ```
   Row 1: Name (header - do not modify)
   Row 2: [Everyone]
   Row 3: [First Employee Name]
   Row 4: [Second Employee Name]
   ...
   ```
5. Role in Column B is optional
6. Save the file

### 5.3 Task Template Setup (Optional)

**Procedure:**

1. Open `Database.xlsx`
2. Navigate to **TaskTemplates** sheet
3. Add frequently used task templates:
   ```
   Column A: TaskName
   Column B: Description
   ```
4. Save the file

---

## 6. Daily Operations

### 6.1 Morning Startup Procedure

**Frequency:** Daily, at start of work day

**Procedure:**

1. **Launch Application**
   - Open `TaskManager.html` in web browser
   - Make sure there's no previous data. You can use "Clear Data" button to clear cache, then refresh the page
   - Import the database usind Drag & Drop or "Choose File" button

2. **Verify Data Currency**
   - Check that today's date is highlighted in date chips
   - Confirm tasks from previous session are displayed

3. **Review Today's Tasks**
   - Click today's date chip to filter tasks
   - Review all-day tasks in sticky header section
   - Review timed tasks in chronological order

4. **Check Pending Assignments**
   - Look for tasks marked "Everyone" that need assignment
   - Assign tasks to appropriate team members

### 6.2 Throughout the Day

**Procedure:**

1. **Monitor Current Time Indicator**
   - Red line shows current time position
   - Current task highlighted with red border

2. **Update Task Status**
   - Change status to "In Progress" when starting work
   - Change status to "Completed" when finished

3. **Use Floating Clock Button**
   - Click clock button to jump to current time
   - Click up arrow to return to top of page

### 6.3 End of Day Procedure

**Frequency:** Daily, at end of work day

**Procedure:**

1. **Update All Task Statuses**
   - Mark completed tasks as "Completed"
   - Verify in-progress tasks reflect current state

2. **Review Tomorrow's Tasks**
   - Click next day's date chip
   - Identify high-priority items for tomorrow

3. **Export Data (Weekly Recommended)**
   - Click "Export to Excel" button
   - Save exported file with date in filename
   - Store in backup location

---

## 7. Task Management Procedures

### 7.1 Creating New Tasks

**Excel Import**

1. Open `Database.xlsx`
2. Navigate to **Tasks** sheet
3. Add new task starting from first empty row (Starting Row 4):

   | Column | Field       | Format                        | Required |
   |--------|-------------|-------------------------------|----------|
   | A      | Date        | MM-DD-YYYY                    | No*      |
   | B      | Time        | h:mm AM/PM                    | No*      |
   | C      | Task        | Text                          | Yes      |
   | D      | Description | Text                          | No       |
   | E      | Priority    | High/Medium/Low               | No       |
   | F      | Assigned    | Employee name                 | No       |
   | G      | Status      | Pending/In Progress/Completed | No       |

   *See Section 7.2 for date/time behavior

4. Save Excel file
5. Import file into Task Manager


### 7.2 Understanding Task Types

| Date      | Time      | Task Type        | Behavior                                   |
|-----------|-----------|------------------|--------------------------------------------|
| Specified | Specified | Timed Task       | Appears on specific date at specific time  |
| Specified | Blank     | All-Day Task     | Appears in sticky section on specific date |
| Blank     | Specified | Everyday Timed   | Appears at that time on ALL dates          |
| Blank     | Blank     | Everyday All-Day | Appears in sticky section on ALL dates     |

### 7.3 Assigning Tasks

**Procedure:**

1. Locate unassigned task (shows "Everyone" badge)
2. Click the "Everyone" assignment badge
3. Select employee name from dropdown list
4. Assignment updates immediately and auto-saves

### 7.4 Updating Task Status

**Status Definitions:**

| Status      | Definition                | When to Use                 |
|-------------|---------------------------|-----------------------------|
| Pending     | Not yet started           | Default state for new tasks |
| In Progress | Currently being worked on | When work begins            |
| Completed   | Finished                  | When task is done           |

**Procedure:**

1. Locate the task to update
2. Click the status badge (yellow/blue/green)
3. Select new status from dropdown
4. Status updates immediately and auto-saves

### 7.5 Setting Task Priority

**Priority Definitions:**

| Priority | Color  | Definition                            |
|----------|--------|---------------------------------------|
| High     | Red    | Urgent, must complete immediately     |
| Medium   | Orange | Important, complete within 30 minutes |
| Low      | Green  | Can be completed within an hour       |

- Definitions are examples and are not being shown in Task Manager UI

**Procedure:**

1. Set priority in Excel before import
2. To change: export data, modify, re-import
3. If not set, they show as Low by default on import 

### 7.6 Filtering and Searching Tasks

**Procedure:**

1. Click "Search" button
2. Enter search criteria:
   - **Text search**: Enter keyword to find in task name/description
   - **Employee filter**: Enter employee name
   - **Status filter**: Enter Pending, In Progress, or Completed
   - **Priority filter**: Enter High, Medium, or Low
3. Click "Search" to apply filter
4. Click "Reset" to clear all filters

**Date Filtering:**

1. Click date chip at top of application
2. Tasks filter to show only selected date
3. Click "Today" chip to return to current date

---

## 8. Data Management

### 8.1 Importing Data

**Procedure:**

1. Prepare `Database.xlsx` with updated data
2. In Task Manager, locate upload area
3. **Option A:** Drag and drop file onto upload area
4. **Option B:** Click upload area, select file from file browser
5. Wait for "Import successful" confirmation
6. Verify tasks display correctly

**Import Notes:**

- Import overwrites existing data in browser
- First 3 rows of Tasks sheet are skipped (headers)
- Invalid dates/times default to everyday/all-day

### 8.2 Exporting Report

**Procedure:**

1. Click "Export to Excel" button
2. File downloads automatically as `TaskManager_Export_[timestamp].xlsx`
3. Exported file includes:
   - Summary dashboard
   - Priority breakdown
   - Status breakdown
   - Employee workload
   - Priority x Status matrix
   - Complete task listing

### 8.3 Clearing Data

**Warning:** This action cannot be undone without a backup.

**Procedure:**

1. Export current data first (recommended)
2. Click "Clear Data" button
3. Confirm the action when prompted
4. All tasks, employees, and templates are removed
5. Browser storage is cleared

---

## 9. Reporting and Analytics

### 9.1 Accessing Analytics Dashboard

**Procedure:**

1. Click "Show Metrics" to expand analytics panel
2. Dashboard displays:
   - Task overview (total, everyday, all-day, scheduled)
   - Priority breakdown with counts
   - Status breakdown with percentages
   - Employee workload distribution
   - Priority x Status matrix

### 9.2 Generating Reports

**Standard Report:**

1. Click "Export to Excel"
2. Open exported file
3. Review pre-formatted sheets:
   - **Summary**: High-level overview
   - **Tasks**: Detailed task listing

**TV Display Mode:**

1. Use TV Export option (if available)
2. Formatted for large screen display
3. Suitable for team dashboards

### 9.3 Key Metrics to Monitor

| Metric                | Target      | Action if Off-Target   |
|-----------------------|-------------|------------------------|
| Pending High Priority | < 3         | Reassign resources     |
| Completed Rate        | > 80% daily | Review blockers        |
| Overdue Tasks         | 0           | Escalate immediately   |
| Unassigned Tasks      | 0           | Assign to team members |

---

## 10. Troubleshooting

### 10.1 Common Issues and Solutions

#### Issue: Tasks not displaying after import

**Possible Causes:**
- Incorrect Excel format
- Column headers modified
- Invalid date/time format

**Solution:**
1. Download fresh template ("Download Template" button)
2. Copy data to new template
3. Verify date format: MM-DD-YYYY
4. Verify time format: h:mm AM/PM
5. Re-import file

#### Issue: Data lost after closing browser

**Possible Causes:**
- Browser cleared localStorage
- Private/incognito browsing mode
- Different browser used

**Solution:**
1. Always use same browser
2. Avoid private/incognito mode
3. Do not clear browser data
4. Export regularly as backup

#### Issue: Current time indicator not showing

**Possible Causes:**
- Not viewing today's date
- No timed tasks for today

**Solution:**
1. Click "Today" date chip
2. Ensure at least one timed task exists for today
3. Refresh browser if needed

#### Issue: Employee names not appearing in assignment dropdown

**Possible Causes:**
- Employee has not been added to the Employees sheet

**Solution:**
1. Open Database.xlsx
2. Verify Employees sheet has names, If not, add employee name
3. Re-import file

### 10.2 Browser-Specific Issues

| Browser | Issue                     | Solution                                 |
|---------|---------------------------|------------------------------------------|
| Safari  | localStorage restrictions | Enable in Safari > Preferences > Privacy |
| Firefox | Private mode data loss    | Use normal browsing mode                 |
| Chrome  | Storage quota exceeded    | Clear other site data                    |

### 10.3 Escalation Path

1. **Level 1:** Check this SOP troubleshooting section
2. **Level 2:** Contact Task Manager Administrator
3. **Level 3:** Report issue on GitHub or Twitter/X (@XPRODUCTIVITY)

---

## 11. Maintenance

### 11.1 Regular Maintenance Tasks

| Task                      | Frequency | Responsible   |
|---------------------------|-----------|---------------|
| Export and backup data    | Daily     | All users     |
| Archive completed tasks   | Weekly    | Administrator |
| Update employee roster    | As needed | Administrator |
| Clear old completed tasks | Monthly   | Administrator |
| Verify backup integrity   | Monthly   | Administrator |

### 11.2 Archiving Completed Tasks

**Procedure:**

1. Export current data
2. Open exported file
3. Create new sheet "Archive_[Month]"
4. Move completed tasks older than 30 days to archive sheet
5. Delete archived tasks from main Tasks sheet
6. Save and re-import

### 11.3 Application Updates

**Procedure:**

1. Export all data before updating
2. Download new `TaskManager.html`
3. Replace old file with new version
4. Re-import data
5. Verify functionality

---

## 12. Revision History

| Version w Standalone TV export | Date          | Author        | Changes              |
|--------------------------------|---------------|---------------|----------------------|
| 1.0                            | November 2024 | XPRODUCTIVITY | Initial SOP creation |

---

## Quick Reference Card

### Keyboard Shortcuts

| Action               | Method                                |
|----------------------|---------------------------------------|
| Jump to current time | Click floating clock button           |
| Return to top        | Click up arrow (when at current time) |
| Filter by date       | Click date chip                       |
| Show/hide metrics    | Click "Show Metrics" / "Hide Metrics" |

### Status Color Codes

| Color  | Meaning     |
|--------|-------------|
| Yellow | Pending     |
| Blue   | In Progress |
| Green  | Completed   |

### Priority Color Codes

| Color  | Meaning         |
|--------|-----------------|
| Red    | High Priority   |
| Orange | Medium Priority |
| Green  | Low Priority    |

### Task Type Icons

| Icon                  | Meaning                              |
|-----------------------|--------------------------------------|
| (none)                | Standard timed task                  |
| (sticky blue section) | All-day task                         |
| Recycle icon          | Everyday task (appears on all dates) |

---

**Document Owner:** @XPRODUCTIVITY
**Review Cycle:** Annually or upon major application updates
