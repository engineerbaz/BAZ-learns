# BeSA Session 04

## DataBase Migration 




### Transition Logs 
Also known as Journal, database log, binary log, or audit log) records all transactions executed on a database

CDC (Change Data Capture)

## AWS Database Migration DMS
Helps you you migrate relational databases 


## Schema

--




---
 **Full Load** - One-time migration of existing data• **Change Data Capture (CDC)** - Continuous replication of ongoing changes• **Full Load + CDC** - Initial migration follow

 ==========
Code :::

unique_id=$(date +%Y%m%d%H%M%S)
session_id=04
file_name=$(git diff --name-only)
git add . && git commit -m "Update: $file_name Session:04 - ID: $unique_id"