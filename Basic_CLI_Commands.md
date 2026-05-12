# Linux CLI Commands — Code Walkthrough

---

# 1. man — Manual Pages (Super Important)

Used to read documentation for Linux commands.

## Syntax

```bash
man <command>
```

## Example

```bash
man ls
```

Opens the manual page for `ls`.

## Useful Navigation Inside man

| Key | Action |
|------|--------|
| q | Quit |
| /word | Search |
| n | Next search result |
| Space | Next page |
| b | Previous page |

---

# 2. cd — Change Directory

Used to move between folders.

## Syntax

```bash
cd <directory>
```

---

## Important Symbols

### . → Current Directory

```bash
cd .
```

Stays in current directory.

---

### .. → Parent Directory

```bash
cd ..
```

Moves one level up.

Example:

```bash
/home/naman/projects
```

After:

```bash
cd ..
```

You move to:

```bash
/home/naman
```

---

### ~ → Home Directory

```bash
cd ~
```

Moves directly to home folder.

Example:

```bash
/home/naman
```

---

### - → Previous Directory

```bash
cd -
```

Moves back to the last visited directory.

Example:

```bash
cd /etc
cd /var
cd -
```

Returns to `/etc`.

---

## Examples

```bash
cd Documents
cd ..
cd ~
cd -
```

---

# 3. mkdir — Make Directory

Creates new folders.

## Syntax

```bash
mkdir <folder_name>
```

## Example

```bash
mkdir projects
```

Creates a folder named `projects`.

---

## Create Multiple Directories

```bash
mkdir dir1 dir2 dir3
```

---

## Create Nested Directories

### -p flag

```bash
mkdir -p project/src/components
```

Creates all parent directories if they don’t exist.

---

# 4. mv — Move or Rename Files

Used to move files/folders or rename them.

---

## Rename File

```bash
mv old.txt new.txt
```

---

## Move File

```bash
mv file.txt Documents/
```

Moves file into `Documents`.

---

## Move Folder

```bash
mv project/ backup/
```

Moves entire folder.

---

# 5. cp — Copy Files and Folders

Copies files/folders.

---

## Copy File

```bash
cp file.txt backup.txt
```

---

## Recursive Copy (Important)

### -r flag

Used to copy folders recursively.

```bash
cp -r project/ backup/
```

Copies entire folder and contents.

---

## Verbose Mode

### -v

```bash
cp -rv project/ backup/
```

Shows files being copied.

---

# 6. ls — List Files and Directories

Displays files/folders.

---

## Basic Usage

```bash
ls
```

---

## Important Flags

### -l → Long Format

```bash
ls -l
```

Shows:

- permissions
- owner
- size
- date

Example output:

```bash
drwxr-xr-x 2 naman naman 4096 May 12 folder
```

---

### -a → Show Hidden Files

```bash
ls -a
```

Shows hidden files like:

```bash
.git
.bashrc
```

---

### -h → Human Readable Sizes

```bash
ls -lh
```

Shows sizes like:

```bash
2K  5M  1G
```

---

### Combined Flags

```bash
ls -lah
```

Most commonly used combination.

---

# 7. pwd — Print Working Directory

Shows current location.

## Syntax

```bash
pwd
```

## Example Output

```bash
/home/naman/Documents
```

---

# 8. rm — Remove Files and Folders

Deletes files/folders.

---

## Delete File

```bash
rm file.txt
```

---

## Delete Folder Recursively

### -r

```bash
rm -r project/
```

---

## Force Delete

### -f

```bash
rm -rf project/
```

⚠ Dangerous command.

Deletes without confirmation.

---

# 9. chmod — Change File Permissions (Super Important)

Controls who can:

- read
- write
- execute

---

# Permission Types

| Symbol | Meaning |
|--------|---------|
| r | Read |
| w | Write |
| x | Execute |

---

# Permission Groups

| Group | Meaning |
|-------|---------|
| User | Owner |
| Group | Group members |
| Others | Everyone else |

---

## Example Permission

```bash
-rwxr-xr--
```

Breakdown:

| Part | Meaning |
|------|---------|
| rwx | User permissions |
| r-x | Group permissions |
| r-- | Others permissions |

---

# Numeric Permission System

| Number | Permission |
|--------|------------|
| 7 | rwx |
| 6 | rw- |
| 5 | r-x |
| 4 | r-- |

---

## Common Examples

### Give Full Permission

```bash
chmod 777 file.txt
```

⚠ Not recommended for sensitive files.

---

### Owner Full Access Only

```bash
chmod 700 script.sh
```

---

### Typical File Permission

```bash
chmod 644 file.txt
```

Meaning:

- Owner → read/write
- Others → read only

---

### Make Script Executable

```bash
chmod +x script.sh
```

Run script:

```bash
./script.sh
```

---

# 10. chown — Change Ownership (Super Important)

Changes file owner.

---

## Syntax

```bash
chown <user> <file>
```

---

## Example

```bash
sudo chown naman file.txt
```

Makes `naman` the owner.

---

## Change User and Group

```bash
sudo chown naman:developers file.txt
```

---

## Recursive Ownership Change

### -R

```bash
sudo chown -R naman project/
```

Changes ownership for entire folder recursively.

---
