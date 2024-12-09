# PDB_Assignment_2024
This repository contains the SQL commands, screenshots, and explanations for creating, managing, and deleting pluggable databases (PDBs) in Oracle. It includes steps for configuring Oracle Enterprise Manager and documenting the process for class activities as part of the PDB Assignment 2024.



ALTER PLUGGABLE DATABASE plsql_class2024db OPEN;


SHOW PDBS;


CREATE PLUGGABLE DATABASE bo_to_delete_pdb 
ADMIN USER bo_plsqlauca IDENTIFIED BY [your_password] 
FILE_NAME_CONVERT = ('/u01/app/oracle/oradata/cdb1/pdbseed/', '/u01/app/oracle/oradata/cdb1/bo_to_delete_pdb/');


ALTER PLUGGABLE DATABASE bo_to_delete_pdb OPEN;

SHOW PDBS;


ALTER PLUGGABLE DATABASE bo_to_delete_pdb CLOSE IMMEDIATE;


ALTER PLUGGABLE DATABASE bo_to_delete_pdb UNPLUG INTO '/u01/app/oracle/admin/cdb1/pdbs/bo_to_delete_pdb.xml';


DROP PLUGGABLE DATABASE bo_to_delete_pdb INCLUDING DATAFILES;
