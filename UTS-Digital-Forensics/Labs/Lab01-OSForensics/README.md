
# Lab 01 - OSForensics Investigation

## Objective

The objective of this lab was to introduce digital forensic investigation concepts and demonstrate how digital evidence can be identified and recovered from a Windows system using OSForensics.

The investigation focused on:

- Creating evidence
- Creating a forensic case
- Locating browser activity
- Searching user activity
- Indexing files
- Discovering evidence using keyword searches

---

## Tool Used

### OSForensics

OSForensics is a Windows forensic investigation toolkit that helps investigators:

- Create investigation cases
- Identify user activity
- Search browser artifacts
- Index files
- Discover digital evidence
- Organise investigation findings

---

## Lab Tasks

### Task 1 – Generate Evidence

To create forensic artifacts for later analysis:

1. Opened Google Chrome
2. Searched for:

```text
Seek Roles
```

3. Visited:

```text
seek.com.au
```

4. Closed the browser

Created a text file on the desktop:

```text
Contacts.txt
```

Added the keyword:

```text
Tony
```

This generated evidence that could later be recovered during the investigation.

---

### Task 2 – Create a Forensic Case

Created a new forensic investigation case within OSForensics.

Case Information:

```text
Case Name: Week 1
Investigator: Student
```

This demonstrated how investigators organise evidence within a structured case environment.

---

### Task 3 – User Activity Analysis

Used the User Activity module to scan the system for evidence.

The scan identified:

- Browser history
- User activity
- Website visits
- Search activity

Evidence recovered:

```text
seek.com.au
```

This demonstrated how browser artifacts may be used as digital evidence during an investigation.

---

### Task 4 – File Indexing

Created an index of desktop text files.

Indexed data included:

- Plain text files
- User-created documents

After indexing completed, the following keyword was searched:

```text
Tony
```

Evidence recovered:

```text
Contacts.txt
```

This demonstrated how investigators can quickly identify relevant files using keyword searches.

---

## Evidence Identified

### Browser Evidence

Examples recovered:

- Search activity
- Website visits
- Browser artifacts
- User browsing history

Example:

```text
seek.com.au
```

---

### File Evidence

Examples recovered:

- Text file contents
- Indexed file information
- User-created documents

Example:

```text
Contacts.txt
Keyword: Tony
```

---

## Screenshots

### Case Creation

Add screenshot:

```text
Screenshots/case-creation.png
```

---

### User Activity Results

Add screenshot:

```text
Screenshots/seek-browser-history.png
```

---

### Search Index Results

Add screenshot:

```text
Screenshots/tony-search-results.png
```

---

## Findings

The investigation demonstrated that normal user activity generates a large amount of digital evidence.

Evidence can be recovered from:

- Browser history
- User activity records
- Text documents
- File content
- Search indexes

OSForensics allows investigators to efficiently locate this information without manually searching through large amounts of data.

---

## Conclusion

Windows systems contain significant amounts of forensic evidence generated through everyday user activity.

Activities such as web browsing and file creation leave artifacts that can later be recovered and analysed by investigators.

This lab demonstrated how forensic tools such as OSForensics can help investigators identify, organise, and analyse evidence efficiently while supporting a structured investigative process.

---

## Skills Demonstrated

- Digital Evidence Identification
- Evidence Collection
- Browser Artifact Analysis
- File Indexing
- Evidence Search Techniques
- Basic Forensic Investigation
- OSForensics Usage
