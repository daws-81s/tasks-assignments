# User and Group Management with Key-Based Authentication

## Objective

This task focuses on managing users and groups on a Linux server, setting up key-based authentication, and ensuring that password-based authentication is disabled.

## Requirements

### 1. User Group Creation
- Create two groups: `devops` and `testing`.

### 2. User Creation and Group Assignment
- Create four users: `ram`, `raheem`, `suresh`, and `philip`.
- Assign `ram` and `raheem` to the `devops` group.
- Assign `suresh` and `philip` to the `testing` group.

### 3. Key-Based Authentication Setup
- For each user (`ram`, `raheem`, `suresh`, `philip`):
  - Generate an SSH key pair.
  - Configure key-based authentication by adding the public key to the user's `authorized_keys` file.
  - Ensure correct permissions are set on the `.ssh` directory and the `authorized_keys` file.

### 4. Disable Password-Based Authentication
- Modify the SSH configuration file to disable password-based authentication, allowing only key-based authentication.

### 5. Testing and Verification
- Verify that each user can log in to the server using their private key.
- Confirm that password-based login attempts are denied.

## Deliverables

### 1. Documentation
- Provide detailed step-by-step instructions used for:
  - Creating groups and users.
  - Generating SSH key pairs and configuring key-based authentication.
  - Modifying the SSH configuration to disable password-based authentication.
- Include logs or screenshots showing:
  - The successful creation of users and groups.
  - Key-based login attempts.
  - Verification that password login is disabled.

### 3. Verification Evidence
- A summary or log demonstrating the following:
  - Successful login attempts using key-based authentication.
  - Failed login attempts using password authentication.

# Permissions Management, Testing, and Verification

## Objective

Extend the previous task by managing file and directory permissions for the created users and groups. This will involve setting specific permissions, testing access, and verifying that permissions are applied correctly. Additionally, you'll modify permissions and observe the changes.

## Requirements

### 1. Directory and File Setup
- Create a directory structure under `/home/devops_projects` for the `devops` group and `/home/testing_projects` for the `testing` group.
  - Inside `/home/devops_projects`, create a subdirectory `project1` with a file `devops_task.txt`.
  - Inside `/home/testing_projects`, create a subdirectory `project2` with a file `testing_task.txt`.

### 2. Set Permissions
- Assign ownership of the `devops_projects` directory and its contents to the `devops` group.
  - Ensure that only members of the `devops` group have read, write, and execute permissions.
- Assign ownership of the `testing_projects` directory and its contents to the `testing` group.
  - Ensure that only members of the `testing` group have read, write, and execute permissions.
- Ensure that the files `devops_task.txt` and `testing_task.txt` are writable only by their respective owners and readable by their respective groups.

### 3. Testing and Verification
- Test access by having each user:
  - Verify that `ram` and `raheem` can access and modify files in the `devops_projects/project1` directory.
  - Verify that `suresh` and `philip` can access and modify files in the `testing_projects/project2` directory.
  - Confirm that users in the `devops` group cannot access files in the `testing_projects` directory and vice versa.

### 4. Change Modifications
- Modify the permissions of the `project1` and `project2` directories:
  - Change permissions so that the `devops_task.txt` file is only readable (not writable) by members of the `devops` group.
  - Change permissions so that the `testing_task.txt` file is only writable (not readable) by members of the `testing` group.
- Test these changes by having each user attempt to read and write to the modified files and directories.
- Document any errors or permission denied messages.

## Deliverables

### 1. Documentation
- Detailed step-by-step instructions used to:
  - Create the directory structure.
  - Set up and modify permissions.
  - Perform testing and verification.
- Logs or screenshots showing:
  - Permission settings for each directory and file.
  - Results of access attempts by different users before and after the permission changes.
  - Any errors encountered during testing.

### 2. Verification Evidence
- A summary of the results showing:
  - Which users were able to access and modify the files as expected.
  - Which access attempts were denied based on the permission settings.

