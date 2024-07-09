# TaskManger-gtk-v1.0
Tastmanager for ubuntu version 24+ needs gtk written in c++ and compiled for use. 



## Task Manager Program User Manual

### Overview

This Task Manager program is a simple graphical application built with GTK+ 3. It provides a user interface to view and manage the running processes of the current user. The main features include displaying a list of running processes with their respective PID, name, and RAM usage, refreshing the process list, and killing a selected process.

### Requirements

- A Linux-based operating system.
- GTK+ 3 development libraries.
- A C++ compiler such as `g++`.
- The `ps` command available in the system.

### Installation

1. **Ensure you have the necessary GTK+ 3 development libraries installed**:
    ```sh
    sudo apt-get install libgtk-3-dev
    ```

2. **Save the source code to a file named `task.cpp`**.

3. **Compile the program**:
    ```sh
    g++ task.cpp -o task_manager `pkg-config --cflags --libs gtk+-3.0`
    ```

4. **Run the program**:
    ```sh
    ./task_manager
    ```

### User Interface

- **Main Window**: The main window displays a list of running processes in a table format. Each row represents a process, showing its PID, name, and RAM usage.

- **Refresh Button**: Located at the bottom of the window, this button refreshes the process list and updates the memory usage status.

- **Kill Process Button**: Also located at the bottom of the window, this button kills the selected process from the list.

- **Memory Status Label**: Displays the total and used memory of the system.

### How to Use

1. **Start the Program**:
    - Execute the compiled `task_manager` program. The main window will appear, displaying the list of running processes.

2. **Refreshing the Process List**:
    - Click the "Refresh" button at any time to update the process list and the memory usage status. This action fetches the latest process data and displays it in the table.

3. **Killing a Process**:
    - Select a process from the list by clicking on it.
    - Click the "Kill Process" button to terminate the selected process. A system command will be executed to kill the process by its PID.

4. **Viewing Memory Status**:
    - The memory status label at the bottom of the window displays the total and used memory of the system, updated each time the "Refresh" button is clicked.

### Error Handling

- **popen() failed**: This error indicates that the program couldn't execute the `ps` command. Ensure that `ps` is installed and available in the system PATH.
- **pclose() failed**: This error indicates that there was an issue closing the pipe after reading the process data. It is generally a non-critical error.
- **Kill Process**: If the selected process couldn't be killed (e.g., due to insufficient permissions), the system command may fail silently. Ensure you have the necessary permissions to kill the process.

### Troubleshooting

- **No Processes Displayed**: Ensure that you are running the program as the same user whose processes you want to monitor.
- **Insufficient Permissions**: Running the program with elevated permissions (e.g., using `sudo`) may be required to kill certain processes.

### Code Structure

- **Process**: A struct representing a running process with PID, name, and RAM usage.
- **MemoryInfo**: A struct representing the total and used memory of the system.
- **RefreshData**: A struct used to pass multiple GTK+ widgets to the signal handlers.

### Compilation and Execution Commands

- **Compilation**:
    ```sh
    g++ task.cpp -o task_manager `pkg-config --cflags --libs gtk+-3.0`
    ```

- **Execution**:
    ```sh
    ./task_manager
    ```

### Support

For any issues or questions, you can contact the developer or refer to the GTK+ documentation for further assistance.

---

