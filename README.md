## An example playbook to run a powershell script on a windows machine 
### To Run

` ansible-playbook -i inventory_windows.yml playbooks/win_ps_nc.yml `
### Example Output
```
SSH password: 

PLAY [Run PowerShell script on Windows] ****************************************

TASK [Ping the Windows machine] ************************************************
ok: [windows_machines_nc]

TASK [Create destination directory] ********************************************
changed: [windows_machines_nc]

TASK [Copy hello.ps1 script] ***************************************************
ok: [windows_machines_nc]

TASK [Run the script] **********************************************************
changed: [windows_machines_nc]

TASK [Verify script success] ***************************************************
changed: [windows_machines_nc]

TASK [debug] *******************************************************************
ok: [windows_machines_nc] => {
    "script_output.stdout_lines": [
        "Hello, this is my script output."
    ]
}

TASK [fail] ********************************************************************
skipping: [windows_machines_nc]

PLAY RECAP *********************************************************************
windows_machines_nc        : ok=6    changed=3    unreachable=0    failed=0    skipped=1    rescued=0    ignored=0
```
