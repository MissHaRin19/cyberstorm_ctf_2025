# Comparison (299 pts)

## Challenge Details
- **Category:** Reverse Engineering
- **Points:** 299
- **Description:**  
  Everyone has started comparing Yamato to Oden since the self-proclamation. Some days, Yamato feels energized, and sometimes belittled. Help Yamato overcome any undue comparisons.

- **Connection Details:**  
  ```bash
  nc cyberstorm.redfoxsec.com 17000
  ```

---

## Approach

### Step 1: Checking the Given File
The challenge provided a file named `easy`. First, we used `cat` to view its contents:
```bash
cat easy
```
The output contained a lot of characters with spaces between them, making it difficult to read.

### Step 2: Extracting Readable Strings
To make the output more structured, we used:
```bash
strings easy
```
This command displayed all readable text line by line. While scanning through the output, we found:
```
The secret code is: 6BKJ0cGB35S3 

```

### Step 3: Sending the Secret Code
To complete the challenge, we needed to send this secret code quickly after connecting via Netcat:
```bash
nc cyberstorm.redfoxsec.com 17000
```
Since the server had a **short timeout**, we had to paste the secret code immediately after connecting. After a few attempts, we successfully submitted the code and retrieved the flag!

---

## Flag
```
REDFOX{1_4M_K0Zuk1_0d3n! }

```
(Replace with the actual flag)

---

## Tools Used
- `cat` (to view file contents)
- `strings` (to extract readable text)
- `nc` (Netcat for interacting with the server)

---


