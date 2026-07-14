#  Lesson 2 - Topic 2A: Manage User Accounts



  ## What I practiced

  Created a user with useradd (comment, expiration, shell, home dir)

  Set/changed password with passwd

  Checked account info with id, whoami, w/who

  Set password aging policy with chage (-m, -M, -W)

  Verified commands with echo $? and exit codes



## Commands I used

 useradd -c "Sara Ahmed" -e 2026-12-31 -s /bin/sh -m saahmed

 passwd saahmed

 chage -m 2 -M 90 -W 7 saahmed

 id saahmed



# Where I got stuck

- ## Where I got stuck
-  Command Flag Confusion: I was initially confused by the overlapping use of chage, passwd, and the -m flag between   different   commands.
-   The Breakthrough: I now understand the difference between the -m flags:
-   In useradd, -m is used to create a home directory.
-   In chage, -m is used to set the minimum days required between password changes.







## Key things I learned



 /etc/passwd = account info (world-readable), /etc/shadow = password hash (root only)



 adduser is interactive, useradd is flag-based



 exit codes are command-specific, check with echo $?



# Lesson 2 - Topic 2B: Group Lifecycle Management (Practice Lab)**


 ## 📋 Scenario Overview**

In real-world system administration, groups undergo changes due to organizational restructuring. In this lab, we simulated a company restructuring where:

The existing support group was renamed to cyber-support to reflect a merger with the cybersecurity team.

 The team verified that group memberships idris and YusufIbrahim) remained intact during the change.

 An unused project group marketing) was decommissioned and permanently deleted from the system.

 Exit statuses were analyzed to verify clean system execution.



## 🛠️ Detailed Lab Steps & Execution**

### Step 1: Renaming the Group groupmod)

To modify group properties, we use the groupmod command. The -n option is used to specify a new name for the group without changing its unique Group ID (GID).

*** Command Executed:**

  **```bash**

  sudo groupmod -n cyber-support support

