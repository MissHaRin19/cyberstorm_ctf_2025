# Big Mom's Plot (100 pts)

## Challenge Details
- **Category:** Reverse Engineering
- **Points:** 100
- **Description:**  
  Big Mom has been keeping their new war strategies under wraps. Not even intelligence services like Cipher Pol have any clue what’s going on. Can you figure out what they are hiding in case the Straw Hat crew comes across their armies again?

- **Connection Details:**  
  ```bash
  nc cyberstorm.redfoxsec.com 4444
  ```

---

## Approach

### Step 1: Connecting to the Server
We used Netcat to interact with the challenge:
```bash
nc cyberstorm.redfoxsec.com 4444
```

### Step 2: Analyzing the Assembly Code
We received an ELF binary in assembly format (`warmup.asm`). The key observations:
1. **User input is read into a buffer** using the `sys_read` syscall.
2. **A loop checks each character** in the input.
3. **If any character is `~` (ASCII 126 or `0x7E`), it prints the flag.**
4. **Otherwise, the program exits.**

### Step 3: Extracting the Flag
Since the program looks for `~`, we simply entered:
```
~
```
After inputting `~`, the server responded with:
```
REDFOX{SO_W3_Wi1L_jU5T_bR1B3_Th3_Mar!n3s_WHIL3_C0mm1t1nG_W4R_Cr1m3s !!} 

```

---

## Tools Used
- `nc` (Netcat) for remote interaction
- `vim`/`nano` for viewing `warmup.asm`
- Assembly analysis to understand program logic

---


