
 **Student:** Mukunzi Prince  
**Student ID:** 20252IMA128  
**Course:** Database Development with PL/SQL (INSY 8311)  
**Instructor:** Eric Maniraguha

## Overview

This assignment covers creating a permanent pluggable database and its user, creating and deleting a temporary PDB, and accessing Oracle Enterprise Manager Database Express.

## Oracle Environment

- Database: Oracle Database 21c Enterprise Edition, version 21.3.0.0.0
- Operating system: Windows 11, 64-bit
- Command-line tool: SQL*Plus
- Container database: `orcl`
- Starter PDB: `ORCLPDB`
- Management interface: Oracle Enterprise Manager Database Express
- Management URL: `https://localhost:5500/em`

## Task 1: Permanent PDB and User

I created `mu_pdb_20252IMA128` from Oracle's seed database, using file-name conversion to give the new PDB its own database files.

I opened the PDB and saved its state so it can reopen automatically when the container database restarts. Verification showed the PDB in `READ WRITE` mode.

Inside this PDB, I created `mukunzi_plsqlauca_20252IMA128` and granted `CREATE SESSION` so the account can connect. I verified that the account status was `OPEN`. This account is retained for future classwork.

Evidence: [PDB creation and user screenshots](screenshots/pdb_creation/).

## Task 2: Temporary PDB Creation and Deletion

I created `mu_to_delete_pdb_20252IMA128` and used `SHOW PDBS` to confirm that it existed.

While the temporary PDB was mounted, I deleted it using `INCLUDING DATAFILES`. A subsequent `SHOW PDBS` confirmed that the temporary PDB was absent and the permanent assignment PDB remained open.

Evidence: [Temporary PDB creation and deletion screenshots](screenshots/pdb_deletion/).

## Task 3: Oracle Enterprise Manager

I accessed Enterprise Manager Database Express at `https://localhost:5500/em` and signed in as `SYSTEM`.

The dashboard displayed the Oracle environment, and its Containers view displayed `MU_PDB_20252IMA128`. The dashboard screenshots include the logged-in username. The SQL*Plus screenshots separately document the temporary PDB's deletion.

Evidence: [Enterprise Manager screenshots](screenshots/oem_dashboard/).

## Challenges and Resolutions

### Initial connection errors

My initial SQL*Plus login attempts returned `ORA-12154` and `ORA-12543`.

I successfully connected locally by setting `ORACLE_SID` to `orcl`, clearing the session's `LOCAL` variable, and launching SQL*Plus from the installed Oracle home using Windows authentication with `AS SYSDBA`.

### SQL*Plus typing error

An incorrectly typed formatting command returned `SP2-0734`. Re-entering `SET LINESIZE 150` correctly resolved the error.

## Integrity Statement

I performed the database operations on my own Oracle installation and captured the screenshots from my own execution. I used AI assistance for guidance, commands, troubleshooting, and preparation of this report. The evidence represents my actual results.

## Submission Details

Repository Link: https://github.com/Mupdeveloper/oracle_pdb_ass_II_20252IMA128_mukunzi  
PDB Name Created: mu_pdb_20252IMA128  
Issues Encountered: Yes
