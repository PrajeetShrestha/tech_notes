# Terminal Folder Manipulation Commands

Navigating and managing folders (directories) in your terminal is a fundamental skill for anyone working with computers. This guide covers the most common commands you'll use on Unix-like systems (Linux, macOS, WSL).

## Essential Navigation & Viewing Commands

* **`pwd`** (Print Working Directory)
  * **Purpose:** Shows you the full, absolute path of your current location in the file system.
  * **Example:**
    ```bash
    pwd
    ```
    *Output:* `/home/youruser/documents`

* **`ls`** (List)
  * **Purpose:** Lists the contents (files and subdirectories) of a directory.
  * **Basic usage (current directory):**
    ```bash
    ls
    ```
  * **List contents of a specific directory:**
    ```bash
    ls /path/to/another/directory
    ```
  * **Long format (detailed information):** Displays file permissions, owner, group, size, modification date, and filename.
    ```bash
    ls -l
    ```
  * **Show all files (including hidden files):** Hidden files typically start with a `.` (e.g., `.bashrc`).
    ```bash
    ls -a
    ```
  * **Combine options (long format and all files):**
    ```bash
    ls -la
    ```

* **`cd`** (Change Directory)
  * **Purpose:** Navigates you from your current directory to another.
  * **Go to a specific directory:**
    ```bash
    cd /path/to/your/target/folder
    ```
  * **Go up one directory level (to the parent directory):**
    ```bash
    cd ..
    ```
  * **Go directly to your home directory:**
    ```bash
    cd
    # or
    cd ~
    ```
  * **Go back to the previously visited directory:**
    ```bash
    cd -
    ```

---

## Creating & Deleting Folders

* **`mkdir`** (Make Directory)
  * **Purpose:** Creates one or more new, empty directories.
  * **Create a single directory:**
    ```bash
    mkdir my_new_folder
    ```
  * **Create multiple directories at once:**
    ```bash
    mkdir folder1 folder2 project_files
    ```
  * **Create parent directories as needed (`-p`):** Useful for creating nested directory structures where intermediate directories might not exist.
    ```bash
    mkdir -p projects/year_2025/q2/report
    ```

* **`rmdir`** (Remove Directory)
  * **Purpose:** Deletes an **empty** directory.
  * **Example:**
    ```bash
    rmdir old_empty_folder
    ```
  * **Important:** This command will fail if the directory contains any files or subdirectories. You'll get an error message like "Directory not empty."

* **`rm -r`** (Remove Recursively)
  * **Purpose:** Deletes a directory and **all its contents** (files and subdirectories). This is a powerful command and **irreversible**, so use it with extreme caution!
  * **Example:**
    ```bash
    rm -r folder_to_delete
    ```
  * **Force removal (`-f`):** Deletes without prompting for confirmation, even if files are write-protected. **Use with even greater care!**
    ```bash
    rm -rf folder_to_delete
    ```

---

## Copying & Moving Folders

* **`cp -r`** (Copy Recursively)
  * **Purpose:** Copies an entire directory and all its contents (subdirectories and files) to a new location.
  * **Example:**
    ```bash
    cp -r source_folder /path/to/destination/
    ```
    This will create `source_folder` inside `/path/to/destination/`.

* **`mv`** (Move / Rename)
  * **Purpose:** Moves a directory to a new location, or renames an existing directory.
  * **Rename a folder:**
    ```bash
    mv old_folder_name new_folder_name
    ```
  * **Move a folder to another location:**
    ```bash
    mv folder_to_move /path/to/another/location/
    ```
    This will move `folder_to_move` into `/path/to/another/location/`.

---

## What Does "Make List" Mean?

The phrase "make list" is not a standard, recognized command in terminal folder manipulation. However, it commonly refers to one of the following intentions:

1.  **Listing Directory Contents:** If your goal is to *display* a list of what's inside a folder, the command you're looking for is **`ls`**.
    * *Example:* `ls -l` will "make" a detailed "list" on your screen.

2.  **Creating a List File:** If you want to *generate a text file* that contains a list of files and folders, you can achieve this by **redirecting the output of `ls` to a file**:
    * ```bash
        ls > my_folder_contents.txt
        ```
        This command takes the standard output of `ls` and writes it into a file named `my_folder_contents.txt`.
    * ```bash
        ls -l > detailed_list.txt
        ```
        This will create a file with a detailed listing.

3.  **Making a Directory:** In some cases, "make list" might be a slight misremembering for "make a directory," which would mean the **`mkdir`** command.
    * *Example:* `mkdir my_list_of_stuff_folder`

In summary, for displaying or creating a file that lists folder contents, `ls` is the command you need.
