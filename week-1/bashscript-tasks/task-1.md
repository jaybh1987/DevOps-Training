### System Maintenance Automation Script
**Objective**:  
Write a Bash script to perform automated system maintenance tasks, including file operations, logging, and scheduling.

#### **Requirements**:

1. **Function Design**
    - Define **three functions**:
        - `add_record`: Adds a new entry to a log file (`/var/log/system_maintenance.log`).
        - `delete_old_files`: Removes files older than `X` days from a specified directory.
        - `backup_files`: Compresses files matching a pattern into a timestamped `.tar.gz` archive.
    - Each function must accept **arguments** (e.g., directory path, retention days).

2. **File Operations (CRUD)**
    - Use `/var/log/system_maintenance.log` as the central log file.
    - **Create**: Initialize the log file if it doesn’t exist.
    - **Read**: Display the last 5 log entries when the script runs.
    - **Update**: Append new log entries with timestamps (e.g., `[2024-05-20 14:00] Task started`).
    - **Delete**: Clean up log entries older than 30 days.

3. **Cron Integration**
    - Schedule the script to run daily at 2 AM:
        - Use `crontab -e` to add the job.
        - Log cron execution (start/end times).

4. **Logging Standards**
    - Log all actions (success/failure) with:
        - Timestamps (`date +"%Y-%m-%d %H:%M:%S"`).
        - Task names (e.g., "BACKUP", "CLEANUP").
        - Error messages (e.g., "Failed to delete file: permission denied").

5. **Argument Handling**
    - Allow command-line arguments to trigger specific functions:
      ```bash
      ./maintenance.sh --backup /home/user/docs 7      # Backup files older than 7 days  
      ./maintenance.sh --cleanup /tmp 30              # Delete files older than 30 days  
      ./maintenance.sh --show-logs                    # Display recent logs  
      ```  
    - Validate inputs (e.g., check if directories exist).

#### **Deliverables**:
1. A Bash script named `maintenance.sh`.
2. Proof of cron job setup (`crontab -l` output).
3. Sample log file (`/var/log/system_maintenance.log`) with at least 10 entries.

#### **Success Metrics**:
- The script runs without errors when tested.
- Logs are generated for all actions.
- Cron job executes the script as scheduled.
