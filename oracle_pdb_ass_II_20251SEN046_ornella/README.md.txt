# Oracle PDB Assignment II

**Student Name:** Kayigirwa Ornella  
**Student ID:** 20251SEN046  
**Course:** Oracle Database Administration  



## Overview of Tasks

This lab exercise required me to use Oracle’s multitenant database architecture. The following four mandatory steps were performed:

1. **Creation of a new Pluggable Database** – Created a permanent PDB and a local user within it.
2.**Creation and Deletion of a PDB** – Created a temporary PDB, tested it, and then deleted it completely.
3. **Setup of Oracle Enterprise Manager (OEM)** – Accessed OEM express and got the dashboard screenshot for the environment.
4.  **Documentation and Reporting** – Documented the whole process and made it available on GitHub.


## Oracle Environment Used

- **Database Version:** Oracle Database 21c Enterprise Edition
- **Container Database:** orcl
- **Tool Used:** Oracle SQL Developer & Oracle Enterprise Manager Database Express


## Task 1: Create a New Pluggable Database

### Naming Convention Used
- **PDB Name:** `or_pdb_20251SEN046`
- **Username:** `ornella_plsqlauca_20251SEN046`
- **Password:** Ornella123

### Steps Performed
1. Connected as SYS with SYSDBA privilege to CDB$ROOT.
2. Created the pluggable database `or_pdb_20251SEN046`.
3. Opened the PDB in READ WRITE mode.
4. Switched into the PDB and created the required local user.
5. Granted necessary privileges (CONNECT, RESOURCE, DBA).

### Evidence
Screenshots are available in the `screenshots/pdb_creation/` folder.


## Task 2: Create and Delete a PDB

### Naming Convention Used
- **Temporary PDB Name:** `or_to_delete_pdb_20251SEN046`

### Steps Performed
1. Created the temporary PDB from the seed.
2. Opened the PDB and verified its existence.
3. Closed the PDB using `CLOSE IMMEDIATE`.
4. Dropped the PDB completely using `DROP PLUGGABLE DATABASE ... INCLUDING DATAFILES`.
5. Confirmed that the PDB no longer exists.

### Evidence
Screenshots are available in the `screenshots/pdb_deletion/` folder.



## Task 3: Oracle Enterprise Manager (OEM)

Successfully accessed Oracle Enterprise Manager Database Express at `https://localhost:5500/em`.

The dashboard clearly shows:
- The CDB environment (ORCL)
- The permanent PDB `OR_PDB_20251SEN046`
- Username SYS visible on the interface

### Evidence
Screenshots are available in the `screenshots/oem_dashboard/` folder.

---

## Challenges Faced and How They Were Solved

1. **Problem: Missing USERS Tablespacel**
When attempting to create the local user `ornella_plsqlauca_20251SEN046`by following tutorials, I met with an error message `ORA-00959: tablespace 'USERS' does not exist`.  
To solve it, i made some research and initially created a new tablespace called `USERS` and then created the user

2. **Connection Problems in the Beginning**  
   Couldn't find the correct SID wheni was trying to make a new connection. I to experiment different SID provided online but then i chose to remain with the connection i had `testDB` with SID which is `orcl`.

3.**Confusion Between Temporary and Permanent Tablespace**  
   At some stage, I mistakenly used the `TEMP` tablespace as the default tablespace, resulting in an error due to the confusion of the query but i followed the notes and solved the issue.

## Integrity Statement

I, Kayigirwa Ornella, confirm that this work is my own. All commands were executed by me, and the screenshots provided are original evidence of the work I performed. 



