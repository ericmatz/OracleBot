# Requirements
## The system must...
- Check what processes are running on a computer
- Store configuration for processes to be tracked
- Start or kill processes
- Control access to each process separately

## The system should..
- Be accessible and controlled via RESTful API
- Be accessible via web server

# Use Cases
## Actor: Administrator
### Add process
    1. The administrator identifies the process & arguments required
    2. The administrator adds the configuration to the system
### Modify Process
    1. The administrator identifies the process and new configuration required
    2. the administrator modifies the configuration
### Delete Process
    1. The administrator identifies the process to be deleted
    2. The administrator removes the configuration
### Get status
    1. The administrator makes a request for a process's state
    2. the system returns the status of the process
### Start Process
    1. The administrator starts a process with the configured settings
    2. The system runs executes the configuration
### Kill Process
    1. The administrator identifies the process to kill.
    2. the system kills the process
        2.a If it is not running return an error
        2.b If it is running under a different PID return an error (Zombie process)
### Add User
    1. The administrator Identifies a user's configuration to add
    2. The administrator adds the user
### Edit User
    1. The administrator Identifies a user and new configuration required
    2. The administrator modifies the user        
### Delete User
    1. The administrator Identifies a user to delete
    2. The administrator deletes the user
### Assign Role
    1. The administrator Identifies a user to grant access to a process
    2. The administrator adds the role to the user
### Revoke Role
    1. The administrator Identifies a user to revoke access from a process
    2. The administrator removes the role from the user
---
## Actor: Unelevated User
### Get Status
    1. The Unelevated user makes a request for a process's state
    2. The system returns the status of the process    
        2.a If it is not public and rights are missing the system rejects the request