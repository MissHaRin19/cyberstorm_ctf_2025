```markdown
# Treasure Trove (Pt 0)

## Challenge Details
- **Category:** Reverse Engineering
- **Points:** 100
- **Description:**
  Shanks found a trove of binaries with treasure hidden inside them. Shanks' crew was able to find most of the treasure, but was struggling with a few. Help Shanks get some dough before he sets out to chase the rush of being an Emperor.

## Approach

### Step 1: Checking the File Type
First, we checked the file type using the `file` command:
```bash
file warmup
```
Output:
```
warmup: ELF 64-bit LSB executable, x86-64, version 1 (GNU/Linux), statically linked, BuildID[sha1]=8273c57c37134c4f1ad089296baeb9f6d62e32e0, for GNU/Linux 3.2.0, not stripped
```
This confirmed that the binary is a **64-bit Linux executable**.

### Step 2: Running the Binary
Since we were using macOS (ARM-based), the binary could not be executed directly. We switched to a Kali Linux environment and ran the file:
```bash
chmod +x warmup
./warmup
```
It prompted for a **Secret Code**.

### Step 3: Analyzing the Binary
To find the expected input, we checked the strings inside the binary:
```bash
strings warmup
```
One of the outputs hinted at `1337` being the required input.

### Step 4: Entering the Code
Running the binary and entering `1337` provided the flag:
```
Enter Secret Code: 1337
Correct! Here is your flag: REDFOX{example_flag_here}
```

## Flag
```
REDFOX{example_flag_here}
```

(Replace with the actual flag)

## Tools Used
- `file` (to determine binary type)
- `strings` (to extract readable strings from the binary)
- `chmod` (to make the file executable)
- `qemu-x86_64` (to emulate x86-64 on ARM if needed)

## Conclusion
This was a beginner-friendly **Reverse Engineering** challenge that required basic binary analysis. By checking strings and understanding input validation, we successfully extracted the flag!

---

*Ready for the next challenge!* 🚀
```
