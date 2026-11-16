# Disk Analysis & Autopsy — Tool Reference

## Autopsy 4.18.0

**Purpose:** Ingest and examine the E01 evidence image, browse extracted content, inspect registry artifacts, review file-system paths, and perform keyword and attribute-based searches.

Views shown in the screenshots include:

- Data Source Summary and Container metadata.
- Extracted Content.
- Operating System Information.
- Operating System User Account.
- Installed Programs.
- Web Bookmarks.
- File System views and Indexed Text.
- File Search by Attributes.
- Keyword Search.

## Windows Registry Analysis

The screenshots show examination of:

- `SYSTEM` for TCP/IP interface values.
- `SOFTWARE` for the `NetworkCards` adapter description.
- Per-user `NTUSER.DAT` for the Desktop wallpaper setting.

## Text / Indexed Text Review

Autopsy's Text or Indexed Text panes are used to inspect readable data from:

- Look@LAN `irunin.ini`.
- PowerShell PSReadLine history.
- PowerShell script content.
- YARA rule source.
- Windows Defender detection records.

## Keyword Search

The keyword search term `zerologon` was used to identify a result associated with the archive filename `2.2.0 20200918 Zerologon encrypted.zip`.

## File Search by Attributes

The file-name search dialog was configured for `.yar` to identify YARA rule files.

> Only Autopsy and the artifacts explicitly visible in the supplied evidence are included. No additional command-line forensic utility is claimed as used.
