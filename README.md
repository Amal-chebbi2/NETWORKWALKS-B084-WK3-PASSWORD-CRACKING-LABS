# 🔐 Password Cracking Labs — John the Ripper (JTR) & NetworkWalks Tools

> Week 3 | Project Modules 1 & 2
> Source: [Networkwalks Academy](https://www.networkwalks.com)

This repository contains two hands-on labs on password cracking applied to a protected PDF file (`My Locked PDF1.pdf`), completed as part of the Cybersecurity & Ethical Hacking course.

The learning goals are to understand:
- The difference between **encryption** (reversible) and **hashing** (one-way function).
- How a hash is extracted from a protected file.
- How a dictionary attack recovers a password from its hash.
- Why weak passwords are a security risk.

---




## 🧩 Module 1 — Password Cracking with John the Ripper (JTR)

**Tools:** John the Ripper (JTR) + Johnny (GUI front-end)

### Summary of steps

| Step | Action |
|---|---|
| 1 | Install John the Ripper (Windows) — or use the version pre-installed on Kali Linux |
| 2 | Install Johnny (GUI) — optional on Kali |
| 3 | Extract the hash from the PDF: <br>• **Windows** → via [onlinehashcrack.com](https://www.onlinehashcrack.com/tools-pdf-hash-extractor.php)
| 4 | Save the hash into `hash1.txt` (format `$pdf$4*4*128*...`) |
| 5 | Load the hash file into Johnny, or run `john hash1.txt` |
| 6 | Start the attack and wait for the result |
| 7 | Display the recovered password: `john --show hash1.txt` |
| 8 | Open the PDF using the recovered password |

### ⚠️ Common mistake
Never open the `.pdf` file directly in Johnny — the hash must first be extracted with `pdf2john.py` (or the online tool), and only the resulting `hash1.txt` file (containing a single line starting with `$pdf$...`) should be loaded.




## 🧩 Module 2 — Password Cracking with Networkwalks Tools

**Tools:** [Hash Calculator](https://networkwalks.com/hash-calculator/) and [Password Cracker](https://networkwalks.com/password-cracker/) — fully browser-based, no installation required.

### Summary of steps

| Step | Action |
|---|---|
| 1 | Download `My Locked PDF1.pdf` |
| 2 | Open the **Hash Calculator**, go to the "PDF" tab |
| 3 | Upload the PDF → the `$pdf$...` hash is generated locally (computed in-browser, nothing is uploaded to a server) |
| 4 | Copy the full hash |
| 5 | Open the **Password Cracker** |
| 6 | Paste the hash into the input field |
| 7 | Start the attack using the built-in wordlist (100 passwords) |
| 8 | Retrieve the displayed password |
| 9 | Open the PDF with that password |

**Expected result:** `password1`

### Advantage
Works identically on Windows, Kali Linux, or macOS, since everything runs inside the browser.

---

## 📊 Comparing the two methods

| Criteria | JTR / Johnny | Networkwalks Tools |
|---|---|---|
| Installation required | Yes (Windows) / No (Kali) | No |
| Interface | CLI or GUI (Johnny) | Web-based |
| Hash extraction | `pdf2john.py` or external site | Hash Calculator (local, in-browser) |
| Wordlist | `rockyou.txt` or custom | Built-in list (100 words) or custom `.txt` upload |
| Professional / real-world use | ✅ Industry-standard tool | 🎓 Educational tool |

---

## 🔑 Key concepts

- **Hash**: a unique, non-reversible fingerprint generated from a password. A hash isn't "decrypted" — candidate passwords are tested until one produces the same hash.
- **Dictionary attack**: tests a list of likely passwords (e.g. `rockyou.txt`, built-in wordlist).
- **Brute-force / incremental attack**: tests every possible combination — slower, but exhaustive.
- **Why it matters**: a short or common password (`password1`, `123456`) can be cracked within seconds to minutes, which is why long, complex, unique passwords are essential.

---

## 📚 References

- [John the Ripper — official site](https://www.openwall.com/john/)
- [Johnny GUI](https://openwall.info/wiki/john/johnny)
- [Networkwalks Hash Calculator](https://networkwalks.com/hash-calculator/)
- [Networkwalks Password Cracker](https://networkwalks.com/password-cracker/)
- [Networkwalks Academy](https://www.networkwalks.com)

---

## ⚖️ Disclaimer

This work is carried out strictly for **educational and ethical purposes** (Ethical Hacking / CEH training), on a PDF file voluntarily provided for the exercise. Cracking passwords on systems or files belonging to third parties without explicit authorization is illegal.

---

*Course: Cybersecurity & Ethical Hacking — Networkwalks Academy*
*Contact: info@networkwalks.com*
